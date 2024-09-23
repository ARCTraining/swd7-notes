When discussing data visualisation, **data encoding** essentially means *how you translate the data into a visual element on a chart* ([Warnes, 2018](https://medium.com/@sophiewarnes/whats-visual-encoding-in-data-viz-and-why-is-it-important-7406bc88b4b4#:~:text=Encoding%20in%20data%20viz%20basically,trying%20to%20say%20or%20show.)). In her fantastic blog post, [Sophie Warnes](https://medium.com/@sophiewarnes/whats-visual-encoding-in-data-viz-and-why-is-it-important-7406bc88b4b4#:~:text=Encoding%20in%20data%20viz%20basically,trying%20to%20say%20or%20show.) describes data encoding as a set of rules to follow, giving the following logic:

> *Every time <data changes in some way>, do <something visual>,*

where the *something visual* is the encoding.

Starting simply, lets consider a scatter plot. We can think about how we might change a point marker to encode the data. There are many different ways we can encode data in this setting, including but not limited to:
- **Position**
    - The *x* and *y* co-ordinates reflect the data
- **Colour**
    - Colour can be used to represent a continuous numerical value (colour map)
    - Colour can be used to represent discrete or categorical data
- **Shape**
    - Marker shape could be used to represent categorical data or highlight specific points
- **Size**
    - Size could be used to represent a continuous numerical value or category

> How many distinct values do you need to discriminate between? This can define the method of encoding that best suits your needs.

We're going to look at two main factors as we discuss encoding data:

##### 1. Truthful and non-misleading graphics
##### 2. Easy to read, efficient graphics

---

Take some time to read through the UCDavis DataLab [Principles of Visual Perception](https://ucdavisdatalab.github.io/workshop_data_viz_principles/principles-of-visual-perception.html) section in their data visualisation workshop notes.

They highlight a number of ways we can be misled by graphics, and how we can leverage the way our brains absorb visual information to build better data visualisations. For example, see the figure below:

![circle visual trick](https://ucdavisdatalab.github.io/workshop_data_viz_principles/img/workshop_data_visualization_tricks_circles_bw.png)

*Caption: Which inner circle is bigger? From [UCDavis Principles of data Visualisation workshop](https://ucdavisdatalab.github.io/workshop_data_viz_principles/principles-of-visual-perception.html#visual-magic-tricks)*

## 1. Building truthful and non-misleading graphics

Refer to [this useful graphic](https://www.oreilly.com/library/view/designing-data-visualizations/9781449314774/ch04.html#use_this_table_of_common_visual_properti) when trying to decide what encoding channel to use.

### Using size as an encoding channel

Size is an attribute that is easy to set to map onto a numerical value, to provide a third dimension to your visualisation. However, there are a few issues with this approach.

#### 1. We are not very good at estimating area
It's difficult to accurately estimate the area of a marker, making it difficult for readers to decode our visualisation. This is also why it's best to [avoid pie-charts wherever possible](https://theconversation.com/heres-why-you-should-almost-never-use-a-pie-chart-for-your-data-214576#:~:text=Pie%20charts%20also%20do%20badly,of%20categories%20in%20one%20pie.&text=The%20tiny%20slices%2C%20lack%20of,make%20interpretation%20difficult%20for%20anyone.).

#### 2. It's not always clear or obvious the component of 'size' that maps onto the value, or how it scales
Different Python plotting libraries tie different marker attributes to the idea of 'size' - marker diameter, radius, and area. This means that different marker shapes masy scale differently for different packages.

Then depending on the scale of your data, you may have to use a multiple or factor to adjust the size relationship to make it visible in your plot. See below for the different effects this can have.

![Size as an encoding channel](image-7.png)

*Caption: Size(s) in matplotlib library set as different mutliples of x value.*

### Implying order

Order can be implied by colour, size, position, angle (of marker). Ensure that you do not unintentionally imply that data are ordered when they are not. When listing data sets in the legend, if there is no scientific basis for ordering them in a specific way, alphabetise them, so as not to unintentionally apply a ranking. For example, country names should be alphabetised inside alphabetised continent headers.

Be mindful when selecting colours for your plots. It's good to keep in mind what colour might represent to your audience, and if this is what you intended. For example, when building a plot discussing political party results, the colours red and blue will have different meanings and interpretation depending on the country. Similarly, using a continuous colour map, or varying saturation and intensity can imply that the data is ordered, as in the above example.

Some things to keep in mind when picking a colour palette for your figure:

1. Is the data ordered or not? Do you need to use a **qualitative**, **sequential** or **diverging** palette?
2. How many levels need to be distinguishable?
3. Will the plot be readable if you have a colour vision deficiency (i.e., colour blindness)?
4. Will the plot be readable if printed in black and white?
5. Is there enough contrast between the different colours that it will be legible on a range of different screens?

You can avail of tools such as [ColorBrewer](https://colorbrewer2.org/) to pick a basic scientific palette. For more fine-grained control, try using [Chroma.js](https://gka.github.io/palettes/#/9|s|00429d,96ffea,ffffe0|ffffe0,ff005e,93003a|1|1) or [Colorgorical](http://vrl.cs.brown.edu/color) to generate palettes.

If you already have a palette in mind, test it out with the fantastic [Viz Palette](https://projects.susielu.com/viz-palette) tool. This will allow you to export hex codes of colours to use in Python.

Further reading:

- [Your Friendly Guide to Colors in Data Visualisation](https://blog.datawrapper.de/colorguide/)
- [Best Color Palettes for Scientific Figures and Data Visualizations](https://www.simplifiedsciencepublishing.com/resources/best-color-palettes-for-scientific-figures-and-data-visualizations#:~:text=How%20to%20Find%20the%20Best,and%20other%20color%20perception%20difficulties.)
"""

heatmaps_md = """
There is a wealth of information and research into choosing the best heatmap to illustrate your data.

[Crameri et al. (2020)](https://www.nature.com/articles/s41467-020-19160-7) highlight some of the issues with using poorly designed heatmaps:

> Zones of danger, such as the boundaries of a hurricane track or current virus spread, are often based on uneven colour gradients to accentuate their importance. [...] Decisions based on data being ‘unfairly’ represented could produce, for instance, a Martian rover being sent over terrain that is too steep as the topography was inaccurately visualised, or a medical worker making an incomplete or inaccurate diagnosis based on uneven colour gradients.

- You can see in the examples above how the `spring` heatmap squashes details at the extremes of the data, so you lose information near the max and minimum values.

- While `jet` allows us to see detail in the extremes of the data, it also produces artifacts due to jumps in lightness between colours.

- The `plasma` colourmap removes these jump artifacts, and allows us to see more in the extreme values than `spring` did.

- The `turbo` colourmap has been designed as a replacement for [`jet`](https://research.google/blog/turbo-an-improved-rainbow-colormap-for-visualization/), where "where perceptual uniformity is not critical, but one still wants a high contrast, smooth visualization of the underlying data". This allows maxima and minima to be clearly seen, and doesn't produce artifical large jumps in brightness.

See the [matplotlib documentation on colour maps for examples](https://matplotlib.org/stable/users/explain/colors/colormaps.html#lightness-of-matplotlib-colormaps).

Other heatmap tools for Python include ["batlow": the Scientific colour map](https://www.fabiocrameri.ch/batlow/), [seaborn colour maps](https://seaborn.pydata.org/tutorial/color_palettes.html#sequential-color-palettes), [cmocean colour maps](https://matplotlib.org/cmocean/), [the SciCoMap package](https://github.com/ThomasBury/scicomap) and the related [blog pot](https://towardsdatascience.com/your-colour-map-is-bad-heres-how-to-fix-it-lessons-learnt-from-the-event-horizon-telescope-b82523f09469)

