# GenCAD Notes

Their website: https://gencad.github.io/

The paper: https://arxiv.org/pdf/2409.16294v1

### Diffusion Models

```vid
https://www.youtube.com/watch?v=fbLgFrlTnGU
Title: What are Diffusion Models?
Author: Ari Seff
Thumbnail: https://i.ytimg.com/vi/fbLgFrlTnGU/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@ariseffai
```



### Latent Diffusion Models

https://en.wikipedia.org/wiki/Latent_diffusion_model

```vid
https://www.youtube.com/watch?v=wuwByIh5kDU
Title: Latent Diffusion Models
Author: William Smith
Thumbnail: https://i.ytimg.com/vi/wuwByIh5kDU/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@WilliamSmith-iy4hy
```

- Diffusion models generate images
- Instead of diffusing directly to pixel "space," you diffuse to an intermediate mapping thats usually of smaller dimension called the "latent space."
- Then, you use another model/algorithm to go from this "latent space" back to pixels

- A *VAE* (Variational Auto-encoder) is the pre-trained model that can encode to and decode from the latent space. 


### Other Terminology

**Autoregressive** means that a model generates one token at a time, then these are strung together. 

