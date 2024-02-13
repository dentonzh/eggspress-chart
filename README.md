
## Eggspress Chart 📊

Eggspress Chart is a component that lets you add charts to your [Eggspress website](https://github.com/dentonzh/eggspress). Under the hood, it uses [react-chartjs-2](https://react-chartjs-2.js.org/) and [Chart.js](https://www.chartjs.org/).

## Installing

Download the zip archive for this repository [using this link](https://github.com/dentonzh/eggspress-chart/archive/refs/heads/main.zip). 

Alternatively, you can click on the "Code" button near the top of the [repository page](https://github.com/dentonzh/eggspress-chart) and click the "Download Zip" button that appears in the menu that appears.

Extract the contents of the zip file to your `my_components` workspace folder. Create this folder if it does not exist.

## How to use

To insert a chart, you must first prepare your data. 

Eggspress Chart can read **CSV files** that most spreadsheet applications and statistical packages support. It can also import directly from Google Sheets files provided they are visible to anyone (i.e. they are public).

### Using CSV files

Place your CSV files in the `my_data` folder of your workspace. Create this folder if it does not exist.

In the content section of a content file, create a new empty line where you would like to insert a chart and write your Chart component:

```markdown

Lorem ipsum dolor sit amet, consectetur adipiscing elit. In gravida libero id molestie volutpat...

<Chart filename="2024-01-records.csv">**Figure 1.** Records for January 2024</Chart>

```

You must include the filename property and pass the filename of the CSV file you'd like to use. This file must exist in the `my_data` folder.

### Using Google Sheets

In your spreadsheet, click the **Share** button on the top-right corner and allow access to "Anyone with this link."

Copy the `file id` for your spreadsheet, which can be found in your address bar between `/d/` and `/edit`.

For example, the `file id` for "https://docs.google.com/spreadsheets/d/17GzyU1WboA5SjsmKLOJGDDXirAXE9MveIKvcy8pOC7o/edit" is "17GzyU1WboA5SjsmKLOJGDDXirAXE9MveIKvcy8pOC7o"

At a minimum, we must pass values to the `filename` and `source` properties of our Chart component.

For `filename`, we will pass in our `file id`. For `source`, we will pass in `"google"`.

In the content section of a content file, create a new empty line where you would like to insert a chart and write your Chart component:

```markdown

Lorem ipsum dolor sit amet, consectetur adipiscing elit. In gravida libero id molestie volutpat...

<Chart filename="17GzyU1WboA5SjsmKLOJGDDXirAXE9MveIKvcy8pOC7o" source="google">**Figure 1.** MTA Daily Ridership Data</Chart>

```

## Customization

You can also pass in additional Markdown content in between the opening (`<Chart>`) and closing (`</Chart>`) tags. This is optional.

There are many other properties you can set that allow you to adjust the type of chart, how your chart's labels appear, and the color palette used.


For detailed usage instructions including a list of all available properties and options, read the [Eggspress Chart docs](https://eggspress.org/blog/eggspress-chart).

> **Important:** You must have both an opening tag and a closing tag when inserting components like Eggspress Chart.

## Removing Eggspress Chart

To remove Eggspress Chart, remove all `<Chart>` tags in your content and delete the file `my_components/Chart.tsx` and the folder `my_components/Chart`.

Alternatively, you can rename the main component file `my_components/Chart.tsx` to `my_components/#Chart.tsx`. This has the effect of replacing all of your `<Chart>` tags with empty elements. It also prevents `<Chart>` from installing any dependencies during build. This is useful if you have many `<Chart>` tags throughout your site where removing these elements would be time consuming and tedious.


