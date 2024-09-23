## Why are you making a figure?
- Is the figure for yourself or direct collaborators? This may be the case if you are quickly checking if results are expected, are pulling together some notes for a supervisory or team meeting, or have some questions for a collaborator about some recent results.

- Is the figure for a scientific publication and so for a broader audience who has technical knowledge but does not know the details of your work specifically?

- Are you presenting a talk or a poster at a conference where the audience are mainly experts in your niche field?

- Is your audience going to be undergraduate students where the aim is to convey a concept or method with your data as an example, instead of conveying your results specifically?

- Is you data visualisation being used in an outreach setting for the general public without any assumed research or field-specific knowledge?

## Who is your audience?

??? note "Yourself!"

    Creating plots and graphs for yourself can be a fantastic way of quickly evaluating datasets, discovering patterns, and validating model output.
    ## Exploratory data visualisation
    This is data visualisation with the intention of discovering something, as opposed to displaying or proving something. The plots generated during the exploratory or investigation stage will likely never make it into a publication or other output: an awful lot of plots generated won't show anything interesting. That's ok! That's the point! Because of this, generating these plots needs to be rapid.

    Exploratory data visualisation for yourself might be...

    - Messy! Labels might be all lowercase, with underscores instead of spaces, and plots might use all default settings for colours.
    - Informal
    - Embedded in notebooks surrounded by exploratory notes
    - Interactive

    ## Interaction can aid exploration
    Interactivity is often not necessary outside of specific applications, and can be overused to hide other issues with a visualisation (such as not knowing the message or story it is supposed to tell), but in the case of exploratory data visualisation it's ok not to know that the message or story is yet!

    Quickly-built interactive visualisations using libraries such as plotly or bokeh can be a useful step in figuring out whether your plot should highlight the overall, large-scale patterns in the data, or if it should zoom in on the details.
    See [this example](figs/example_1.html).

    ## Captions
    Captions do not have to be as formal when building an exploratory plot for yourself; however it's still useful to tag any figures with your notes. This could be by adding some markdown text in a Jupyter notebook after the figure (shown above in italics), or by adding info to the title. It's easy to forget what info you have gleaned from a particular plot, and noting it down like this can help save you time repeating yourself.



??? note "Your research group or collaborators"

    ## Informality depends on context

    For quick meetings, exploratory plots without much formatting might be sufficient; however, bear in mind whether you are meeting in-person to talk through the plot or whether the work needs to be able to stand on its own alongside an explanatory note.

    While the plots might still be somewhat exploratory, and you may want to maintain some interaction for discussion, it's likely you'll want to have a better idea of the message or key result behind the plot. We'll discuss this more in Section 2: Story

    While in a publication, you would pick one plot that best highlights a particular pattern or feature, when putting together figures for discussion it can be useful to provide a few different but similar views to help discover the most useful way of presenting the data.
    For example, [this figure](figs/example_2.html) and [this figure](figs/example_3.html) could be discussed at a meeting.

    ## Captions
    Again, captions are really useful for giving your collaborators a peek inside your thought process. They can be conversational and open ended, but should convey what message you think might be lurking in the data.

??? note "Specialists in your domain"

    ## Domain-specific plots
    Certain research areas will have niche, domain-specific plots, that will be easily understandable by people within that field but would look unusual or confusing to someone outside. These sort of plots which require specialist knowledge can be very useful in quickly imparting detailed information. For example, the ternary plot used for determining the provenance of sedimentary samples will be immediately recognised by those working in geology or a related field.
    
    ## Captions
    Captions should be detailed and define every piece of visual information in the figure. A non-specialist should still be able to determine the main message of your plot after reading the caption, even if the layout of the plot is new to them.

??? note "Researchers outside your domain"

    A more general research audience may require more hand-holding to digest niche or complex plots. This can be done by reducing the amount of information being conveyed in the plot, by incorporating helpful labels, or by creating multiple panels and splitting up the data.

    Some useful questions to ask include:

    - What are common scientific/research terms, and what might be terms only understood by researchers in your specific field?
    - What are some common assumptions in your field that might not be true of other domain areas, and will require explanation?

??? note "General public"

    More illustrative or infographic-style plots are often popular when designing data visualisation for the general public; however, more quant-style plots are also often needed. In general, it is useful to label your data clearly and avoid unexplained scientific jargon—this is true of all data vis, but becomes especially necessary when presenting to non-technical audiences.

    In general, all the follow-on rules and guidelines we discuss in later sections are more important for figures created for the general public: other, more specialist audiences will be more forgiving of bad design choices as they have been trained to read scientific visualisations.

    Some useful questions to ask yourself include:

    - Do we need to convey detailed number or can we focus instead on trends?
    - How busy are our plots? Can we strip them down and split data up into different plots?
    - How much information are we trying to deliver in each plot? Try to stick to one key message or piece of information.

## What's the context and the medium?


??? note "Where will your visualisation be shown?"

    ### Is it going to be quickly viewed on a large projector screen as part of a presentation, with you talking over it?
       - Possibly reveal features slowly, adding data as you explain
       - Large font size and thick lines/large markers
       - Should be rapidly digestible
       - Your spoken word can act as a caption to explain the plot to the audience
    ### Will it be part of a published research article?
       - Can expect people to spend a little longer reading it and absorbing the content
       - Can include a lot of detail in the caption
       - Will need to meet very specific dimension, font size and resolution specifications
    ### Will it be presented on a poster?
       - Make it large enough to be comfortably read from a distance
       - Be careful defining size and resolution to ensure it can be printed in large format
       - Depending on the context, you may need to play around with features such as transparency and colour palette to ensure your graphic is legible.

