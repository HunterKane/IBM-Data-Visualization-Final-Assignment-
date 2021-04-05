# IBM-Data-Visualization-Final-Assignment-

# Assignment

-   [Story](#story)
-   [Components of the report items](#components-of-the-report-items)
-   [Expected layout](#expected-layout)
-   [Requirements to create the dashboard](#requirements-to-create-the-dashboard)
-   [What is new in this exercise compared to other labs?](#what-is-new-in-this-exercise-compared-to-other-labs?)
-   [Review](#review)
-   [Hints to complete TODOs](#hints-to-complete-todos)
-   [Application](#application)

## Story:

As a data analyst, you have been given a task to monitor and report US domestic airline flights performance. Goal is to analyze the performance of the reporting airline to improve fight reliability thereby improving customer relaibility.

Below are the key report items,

-   Yearly airline performance report 
-   Yearly average flight delay statistics

_NOTE:_ Year range is between 2005 and 2020.

## Components of the report items

1.  Yearly airline performance report 

    For the chosen year provide,

    -   Number of flights under different cancellation categories using bar chart.
    -   Average flight time by reporting airline using line chart.
    -   Percentage of diverted airport landings per reporting airline using pie chart.
    -   Number of flights flying from each state using choropleth map.
    -   Number of flights flying to each state from each reporting airline using treemap chart.
2.  Yearly average flight delay statistics

    For the chosen year provide,

    -   Monthly average carrier delay by reporting airline for the given year.
    -   Monthly average weather delay by reporting airline for the given year.
    -   Monthly average natioanl air system delay by reporting airline for the given year.
    -   Monthly average security delay by reporting airline for the given year.
    -   Monthly average late aircraft delay by reporting airline for the given year.

    _NOTE:_ You have worked created the same dashboard components in `Flight Delay Time Statistics Dashboard` section. We will be reusing the same.

## Expected Layout

<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork/labs/Module%205/Layout.png" width="2000" alt="cognitiveclass.ai logo"/>
</center>



## Requirements to create the dashboard

-   Create dropdown using the reference [here](https://dash.plotly.com/dash-core-components/dropdown?cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)
-   Create two HTML divisions that can accomodate two components (in one division) side by side. One is HTML heading and the other one is dropdown.
-   Add graph components. 
-   Callback function to compute data, create graph and return to the layout.

## Review

Search/Look for review to know how commands are used and computations are carried out. There are 7 review items.

-   REVIEW1: Clear the layout and do not display exception till callback gets executed.
-   REVIEW2: Dropdown creation.
-   REVIEW3: Observe how we add an empty division and providing an id that will be updated during callback.
-   REVIEW4: Holding output state till user enters all the form information. In this case, it will be chart type and year.
-   REVIEW5: Number of flights flying from each state using choropleth
-   REVIEW6: Return dcc.Graph component to the empty division
-   REVIEW7: This covers chart type 2 and we have completed this exercise under Flight Delay Time Statistics Dashboard section

## Hints to complete TODOs

### TODO1

Reference [link](https://dash.plotly.com/dash-html-components/h1?cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

-   Provide title of the dash application title as `US Domestic Airline Flights Performance`.
-   Make the heading center aligned, set color as `#503D36`, and font size as `24`.
    Sample: style={'textAlign': 'left', 'color': '#000000', 'font-size': 0}

### TODO2

Reference [link](https://dash.plotly.com/dash-core-components/dropdown?cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

Create a dropdown menu and add two chart options to it.

Parameters to be updated in `dcc.Dropdown`:

-   Set `id` as `input-type`.
-   Set `options` to list containing dictionaries with key as `label` and user provided value for labels in `value`. 

    _1st dictionary_

    -   label: Yearly Airline Performance Report
    -   value: OPT1

    _2nd dictionary_

    -   label: Yearly Airline Delay Report
    -   value: OPT2
-   Set placeholder to `Select a report type`.
-   Set width as `80%`, padding as `3px`, font size as `20px`, text-align-last as `center` inside style parameter dictionary.

#### Skeleton:

```
  dcc.Dropdown(id='....', 
                   options=[
                           {'label': '....', 'value': '...'},
                           {'label': '....', 'value': '...'}
                           ],
                  placeholder='....',
                  style={....})
```

### TODO3

Add a division with two empty divisions inside. For reference, observe how code under `REVIEW` has been structured.

Provide division ids as `plot4` and `plot5`. Display style as `flex`.

#### Skeleton

```
html.Div([
         html.Div([ ], id='....'),
         html.Div([ ], id='....')
         ], style={....})
```

### TODO4

Our layout has 5 outputs so we need to create 5 output components. Review how input components are constructured to fill in for output component.

It is a list with 5 output parameters with component id and property. Here, the component property will be `children` as we have created empty division and passing in `dcc.Graph` after computation.

Component ids will be `plot1` , `plot2`, `plot2`, `plot4`, and `plot5`.

#### Skeleton

```
[Output(component_id='plot1', component_property='children'),
 Output(....),
 Output(....),
 Output(....),
 Output(....)]
```

### TODO5

Deals with creating line plots using returned dataframes from the above step using `plotly.express`. Link for reference is [here](https://plotly.com/python/line-charts?cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

Average flight time by reporting airline

-   Set figure name as `line_fig`, data as `line_data`, x as `Month`, y as `AirTime`, color as `Reporting_Airline` and `title` as `Average monthly flight time (minutes) by airline`.

#### Skeleton

```
carrier_fig = px.line(avg_car, x='Month', y='CarrierDelay', color='Reporting_Airline', title='Average carrrier delay time (minutes) by airline')`
```

)

### TODO6

Deals with creating treemap plot using returned dataframes from the above step using `plotly.express`. Link for reference is [here](https://plotly.com/python/treemaps?cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork-20297740&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

Number of flights flying to each state from each reporting airline

-   Set figure name as `tree_fig`, data as `tree_data`, path as `['DestState', 'Reporting_Airline']`, values as `Flights`, colors as `Flights`, color_continuous_scale as `'RdBu'`, and title as `'Flight count by airline to destination state'`

#### Skeleton

```
tree_fig = px.treemap(data, path=['...', '...'], 
                      values='...',
                      color='...',
                      color_continuous_scale='...',
                      title='...'
                )
```

