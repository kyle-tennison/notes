# Landau Video 2 Script

### Introduction

Hi, my name is Kyle. I'm a 2nd year undergraduate at Georgia Tech, and this video is the second part in a little series I'm doing in which I derive the conservation of energy from classical mechanics. In the last video, we derived the Euler Lagrange equation, which is:

$$\frac{\partial L}{\partial q}-\frac{d}{dt}\bigg ( \frac{\partial L}{\partial \dot q} \bigg ) = 0 $$

In this video, I wanted to talk about Galileo's relativity principle, but before I get to that, I wanted to explore the principle of least action a little more. For those who don't know, the principle of least action takes this form:

$$S = \int _{t_0}^{t_1}L(q, \dot q, t)dt$$

By using variational calculus, we can derive the Euler Lagrange equation from this.

### Total Time Derivatives

So, let's imagine two Lagrangians: $L$ and $L'$. We'll say that

$$L' = L + \frac{d}{dt}\big(f(q, t)\big).$$

In other words, the only difference between $L$ and $L'$ is the total time derivative of some function of position and time.

Let's look at what happens when we put this into the principle of least action. Notice that we'll get something like this:

$$S'=\int_{t_0}^{t_1}L'(q, \dot q, t) dt = \int_{t_0}^{t_1} L(q, \dot q, t) dt + \int_{t_0}^{t_1}\frac{d}{dt}(f(q, t)) dt$$

Then, via the fundamental theorem of calculus, which is:

$$\int_a^b f(x) dx = F(b)-F(a)$$

where $\frac{dF}{dx}=f$, we can say that:

$$S'=\int_{t_0}^{t_1}L(q, \dot q, t) dt + f(q(t_1), t_1)-f(q(t_0), t_0)$$

Notice that we are effectively adding a constant to the action.

In the previous video, we talked about the calculus of variations. If you remember, we started by replacing $q$ with $q' = q+\epsilon \delta q$. Then, we plotted $S'$ against $\epsilon$ to see how the error increased with $\epsilon$. Next, we took the derivatives of both sides with respect to $\epsilon$ to find the value that minimized the action. Because this term (the $+ f(q(t_1), t_1)-f(q(t_0), t_0)$) is a constant, it disappears when we take this derivative. If this seems foreign, watch the last video that goes through this process step by step; I have a link in the description. Also, if you're curious about what forms $f$ can take—like, say, if there are velocity or acceleration terms in here—I linked a physics [stack exchange discussion](https://physics.stackexchange.com/questions/112036/when-can-we-add-a-total-time-derivative-of-fq-dotq-t-to-a-lagrangian) in the description.

So anyway, what does all of this mean? Because our function $f$ disappears in the process of deriving the Euler Lagrange equations, *and* because the Euler Lagrange equations dictate the equations of motion, we can say that if two Lagrangians differ by a total time derivative, then their equations of motion will be the same.

### Galileo's Relativity Principle

So, let's step aside from this total time derivative thing for a second to talk about Galileo's relativity principle. His principle says that:

A system's equations of motion are the same in all inertial frames.

Let's unpack this by looking into what an inertial frame is.

### Inertial Frames

An inertial frame is usually described as one that "isn't accelerating." This is usually good enough for most applicable physics, but this definition is weak. Acceleration, as we all know, is the second time derivative of position. And, because there is no absolute position in the universe, we are always measuring position relative to something else.

Now, if the point with respect to which we are measuring our position is *also accelerating*, we may inadvertently deem our frame—which is also accelerating—as inertial. So, it's evident that we need a better way to define inertial frames.

The way we do this is by stating the following:

If the following are true, then we are in an inertial frame:
1. Space is homogeneous.
2. Space is isotropic.
3. Time is homogeneous.

First, let's define these terms. Homogeneous means that something consists of parts all of the same kind. In the context of space and time, we are saying that all positions in space are created equal, and similarly, all instants of time are created equal.

Now, what would this mean in the context of classical mechanics? If the equations of motion in our reference frame change depending on where our frame is, then we would violate the first clause. Similarly, if the equations of motion change depending on when we do an experiment, this would violate the third clause. As for the second clause, if our equations of motion depend on the orientation of our reference frame in space, then we are observing anisotropy of space.

This is a lot to unpack, so let's imagine some scenarios that might break these rules. If my reference frame is on a spinning disk, like a merry-go-round, I will notice that:
1. The equations of motion change depending on where my frame sits on the disk. The centrifugal force would change depending on where my particle is in my frame and, more importantly, where the frame is. This violates the first clause.
2. The orientation of the frame also matters. If I were to rotate it 90°, the ball would change from accelerating from the right of the frame to the top of the frame. This shows directionality in the equations of motion, which violates the second clause.
3. Now, imagine that this disk's angular velocity is a non-uniform function of time. For instance, say it spins twice as fast after 3:00; this would mean that our equations of motion will change with time, which violates the third clause.

Now, if we instead made our frame encompass the disk itself, and we neglected things like the rotation of the Earth, then we could say that the frame is inertial. So, if we zoom out enough, we can always find an inertial frame.

Now, I want to make a few comments. Here, I said that our equations of motion cannot change with time. This isn't to say that the equations of motion cannot depend on time; they just can't depend on absolute time. Think about a spring oscillating. I get to choose when I start the timer, and I expect the displacement over time to be the same every time I do the experiment—provided I don't mess anything up.

Now, if time were to lack homogeneity, then I wouldn't get to arbitrarily pick when to start my stopwatch; I would need to have some knowledge of how my reference frame depends on time. Imagine I was performing this experiment on this merry-go-round that is twice as fast after 3:00; in this scenario, I would need to also know what time of day it is and then adjust my equations accordingly.

When we pick an inertial frame, we are simplifying the problem so we don't have to deal with things like this. We allow the "origin" of time to be an arbitrary pick that best simplifies our problem.

Then, I also wanted to add another comment about the isotropy of space. When I first read through this, I was wondering why gravity on Earth didn't constitute a non-inertial frame. After all, it seems that any Earth-bound frame would have a bias downwards. If I had a frame accelerating at $9.81\ m/s^2$, then the laws of motion would be exactly equivalent, and yet somehow this frame is non-inertial.

This is a nontrivial question, and Einstein himself addresses it in his general relativity. But, for classical mechanics, we treat objects on Earth as if they were in a potential energy field, which I will discuss later.

### Free Particle

For now, let's imagine what the simplest system looks like: a free particle without any potential energy. Think of a rock in deep space—it will only do something if we push it.

For this Lagrangian, we can make quite a few simplifications. Firstly, because there is no potential energy and because we know space to be homogeneous, our Lagrangian won't depend on position.

Secondly, because our frame is inertial, we know that it won't depend on time.

Finally, again because our frame is inertial, we know that it shouldn't depend on direction. However, we have this term $\dot q$, which is a velocity vector. If we're using Cartesian space, this would look something like $\dot q = \langle \dot x, \dot y, \dot z \rangle$, which certainly has direction. To remove direction, we can raise $q$ to an even exponent; I'll use the power of two. This means that our $\dot q$, which I'll call $v$, is $||\dot x^2 + \dot y^2 + \dot z^2||$, which is a scalar quantity.

My choice to use two here isn't entirely arbitrary. I'll show you why we can't really use other powers in a moment.

So now our Lagrangian is some function of $L(v^2)$. Now, let's try to observe Galileo's relativity principle for this free particle. Let's say that we have another system with the Lagrangian $L'$ that is moving at a tiny constant velocity $\epsilon$, relative to the other system. So, both systems could be moving; only this one is moving with a small difference in velocity of $\epsilon$. We can express this new Lagrangian $L'$ using $L$ with:

$$L' = L(v') = L(v^2 + 2\textbf{v}\cdot \epsilon + \epsilon ^2)$$

So think about what we're doing here. We're shifting $L$ from $L(v^2)$ to $L(v^2+2\textbf{v}\cdot \epsilon + \epsilon ^2)$, which is a shift of $2\textbf{v}\cdot \epsilon + \epsilon^2$. This shifting of a function might sound a little bit familiar, and in fact, this is what a Taylor series is for. In case we aren't familiar, a Taylor series allows us to say:

$$f(x_1)=f(x_0)+f'(x_0)(x_1-x_0) + \cdots $$

In this case $f = L$, $x_0 = v^2$, and $x_1 = v'^2$. We can hence say:

$$L(v'^2) = L(v^2)+\frac{d L}{d v^2}(v'^2-v^2)+\cdots$$

> We can use total derivatives because $L$ solely depends on $v^2$

Let us neglect the higher order terms and replace $v'^2 - v^2$ with $2\textbf{v}\cdot\epsilon$, neglecting the $\epsilon ^2$ term that will vanish as we let $\epsilon \to 0$. This yields:

$$L(v'^2) = L(v^2) + \frac{d L}{d v^2}(2 \textbf{v} \cdot\epsilon)$$

> $\textbf{v} \cdot \epsilon$ is a constant, so isotropy of space is not violated

Great. Now we can start pulling in the total time derivative stuff that we mentioned before. Galileo's relativity principle says that these two Lagrangians should have equivalent laws of motion, but this can only be true if they differ by a total time derivative. So, we have to ask ourselves if $\frac{\partial L }{\partial v^2}(2\textbf{v} \cdot\epsilon)$ is a total time derivative.

If $\frac{\partial L }{\partial v^2}$ is a constant, then we have a linear function of velocity, which is indeed a total time derivative. And, we know that $\frac{\partial L }{\partial v^2}$ cannot have other $q$ or $t$ terms in it—otherwise this would invalidate Galileo's relativity principle. So, if we know $\frac{\partial L }{\partial v^2}$ is constant, what does it mean? This value, as is observed by experiment, is simply $m/2$. I wish there was a better way to prove this, but I'm not sure of any conventional way to go about that.

So, now we're saying:

$$\frac{d L}{d v^2}=\frac{m}{2}$$

Then, integrating with respect to $v^2$ gives:

$$L=\frac{1}{2}mv^2+C$$

And, as I mentioned, adding a constant to the Lagrangian doesn't have any physical meaning because it gets ignored during the calculus of variations, so we can ignore this $C$.

Now, let's not forget about the other Lagrangian $L'$. Now that we know $L$, we can find $L'$:

$$L'=\frac{1}{2}mv'^2=\frac{1}{2} (v^2+2\textbf{v}\cdot\epsilon)=\frac{1}{2}mv^2+mv\epsilon$$

Because $mv\epsilon$ is a linear function of $v$, it is a total time derivative, and hence does not influence the equations of motion.

So now we can see that the Lagrangians $L$ and $L'$ will have equivalent equations of motion because of this total time derivative rule. This hopefully shows how Galileo's relativity works out mathematically.