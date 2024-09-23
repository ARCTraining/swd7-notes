# SWD7 - Introduction to Data Visualisation with Python

This course is designed to introduce concepts relating to good data visualisation, utilising packages available for Python.

This course should be useful for anyone who works with data and needs to visualise results. While the term “scientific data visualisation” is used in this documentation due to the sources we have collated, the subject matter and example datasets should be applicable to wider research areas than STEM.

This course focuses on the production of static visualisations, and not interactive dashboards.

# Delivery Guidelines

This course contains a number of interactive elements; a devcontainer that can be launched on GitHub codespaces is provided, and links are given to lunch Jupyter notebooks in your Colab account.

## Dev container for introduction section

**Before delivering the course**: launch the codespace in your account and check that it builds correctly; it will take a few minutes to "boot up" and install the required Python dependencies. Note that a new terminal will open as it runs `pipx install requirements.txt`.

Test that the interactive presentation works:

`streamlit run app.py`

This should forward to port 8501, and a dialogue should pop up allowing you to view this in a new browser tab.

## Notebooks

On the docs page `Practical Session/How to use this resource` there are a list of Colab links which will launch the partially-completed notebooks in your browser, for you to save to your Google Drive and edit with Colab. The attendees can also follow these links to get a template for the session. The full "solution" notebooks are then provided, numbered 1-5.

## Suggested timetable

Note: the practical sessions should be largely self-directed, and shouldn't be delivered as just following live coding. Instead, they should be a conversation back and forth, encouraging attendees to attempt different exercises and adapt the materials. They should also involve screen breaks.

| Session | Time | Duration |
|---------|------|----------|
| Intro presentation 1 (slides) | 9.40 am - 10.00 am | 20 mins |
| Brief break | | |
| Interactive introduction section (see devcontainer instructions above) | 10.10 am - 10:50 am | 40 mins |
| Brief break | | |
|Practical Session 1: An introduction, Exploratory data vis (2 notebooks) | 11.00 am - 12.00 pm | 1 hour (with breaks) |
| Lunch | 12.00 pm - 13.00 pm | 1 hour |
| Practical Session 2: Leveraging external libraries | 13.00 pm - 13.40 pm | 40 mins|
| Brief break | | |
| Practical Session 3: Composition of multi-panel and gridded plots | 13:50 pm - 14:30 pm | 40 mins |
| Brief break | | |
| Practical Session 4: Exploring heatmaps and legends | 14:40 pm - 15:20 pm | 40 mins |
| Brief break | | |
| Practical Session 5: Exploring a dataset | 15:30 pm - 16:20 pm | 50 mins |
| Final Q&A | until 16:30 | 10 mins |
