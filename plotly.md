# Plotly

## Starter

```
import plotly import offline as py, graph_objs as go, tools, figure_factory as ff
py.init_notebook_mode(connected=True)
```

### Use Seaborn's color pallete

```python
def colorscale_from_seaborn(palette_name):
  cmap = sns.color_palette(palette_name)
  n = len(cmap)
  colorscale = []
  for idx, c in enumerate(cmap):
    rgb = (np.array(c) * 255).astype(int)
    colorscale.append([idx / (n - 1), 'rgb({},{},{})'.format(*rgb)])
  return colorscale
```

## Databricks

```python
def display_plotly(fig):
  displayHTML(py.plot(fig, output_type='div'))
```
