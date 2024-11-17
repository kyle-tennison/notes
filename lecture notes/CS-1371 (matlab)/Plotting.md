# Plotting

### Basic 2D Plots
- **Command**: `plot()`
- **Usage**: Creates a 2D line plot of data.
- **Syntax**:
  ```matlab
  x = 0:0.1:10;       % Define x-axis data
  y = sin(x);         % Define y-axis data
  plot(x, y);         % Plot x vs. y
  xlabel('x');        % Label for x-axis
  ylabel('sin(x)');   % Label for y-axis
  title('Sine Wave'); % Title of the plot
  ```

### Customizing Plots
  ```matlab
  plot(x, y, 'r--o', 'LineWidth', 2); % Red dashed line with circular markers
  grid on;                            % Turn on grid
  legend('Sine Curve');               % Add legend
  ```


The pattern for plot style follows `{color} {linetype} {marker type}`. 

For example,
- `ro` has color `r`, no line type (so no line), and `o` type markers
- `b--d` is a dashed blue line with diamond markers

The *line options* are:
- `-` solid
- `:` dotted
- `-.` dashdot
- `--` dashed
-  leave empty for no line

The *marker options* are:
- `.` point
- `o` circle
- `x` x-mark
- `+` plus
- `*` start
- `s` square
- `d` diamond
- `p` pentagram



### Multiple Plots in the Same Graph
To plot multiple lines on the same graph, you can use the `plot` function with multiple `x, y` pairs:
  ```matlab
  y1 = sin(x);
  y2 = cos(x);
  plot(x, y1, '-b', x, y2, '--r');    % Blue solid line for y1 and red dashed line for y2
  ```

### Subplots
If you want multiple plots in one figure window, you can use the `subplot` function:
  ```matlab
  subplot(2, 1, 1); % 2 rows, 1 column, position 1
  plot(x, y1);
  title('Sine Wave');

  subplot(2, 1, 2); % 2 rows, 1 column, position 2
  plot(x, y2);
  title('Cosine Wave');
  ```

You effectively select the subplot, then run commands that will automatically map to that subplot.

If you want to make an axis square, you can run the `axis square;` command.
### 3D Plots
MATLAB supports 3D plotting as well. Common types are surface plots, mesh plots, and 3D line plots.

- **Mesh Plot**:
  ```matlab
  [X, Y] = meshgrid(-5:0.5:5, -5:0.5:5);
  Z = sin(sqrt(X.^2 + Y.^2));
  mesh(X, Y, Z);      % Creates a wireframe plot
  title('3D Mesh Plot');
  ```

- **Surface Plot**:
  ```matlab
  surf(X, Y, Z);      % Creates a surface plot
  shading interp;     % Smooth shading
  colorbar;           % Display color bar
  ```

### Specialized Plots
MATLAB also includes built-in functions for various types of specialized plots:
- **Histogram**: `histogram(data);`
- **Bar Plot**: `bar(x, y);`
- **Scatter Plot**: `scatter(x, y);`
- **Pie Chart**: `pie(data);`

### Hold
If you want to draw two plots atop each other, you can use `hold on` and `hold off`. When you toggle `hold on`, consecutive plots will not clear the canvas and multiple plots can be drawn atop each other.

```matlab
% Plot the first set of points (e.g., black stars)
plot(x, y1, 'k*', 'MarkerSize', 10);
hold on;          % Retain the current plot, so the next plot overlays it

% Plot the second set of points (e.g., green pluses)
plot(x, y2, 'g+', 'MarkerSize', 10);
hold off;         % Turn off hold
```

