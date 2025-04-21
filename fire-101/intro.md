# Welcome to the Set Your Money on FIRE Jupyter Book

This book is designed to help you understand the basics of financial planning and investing while introducing you to the Financial Independence Retire Early (FIRE) concept.  It shows off some interactive examples demonstrating compound interest and retirement planning.

```{tableofcontents}
```


```{shinylive-python}
import shiny
from shiny import ui, render

app = shiny.App(
    ui.page_fluid(
        ui.input_slider("n", "Number of bins", 1, 100, 50),
        ui.output_plot("plot")
    ),
    server=lambda input, output: output.plot(render.plot(lambda: plt.hist(np.random.randn(1000), bins=input.n())))
)
app.run()
