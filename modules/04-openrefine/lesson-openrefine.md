# OpenRefine Lesson

>OpenRefine is a Java-based power tool that allows you to load data, understand it, clean it up, reconcile it, and augment it with data coming from the web. All from a web browser and the comfort and privacy of your own computer [openrefine.org]

OpenRefine does not install like a regular application. It uses your web browser to visualize and carryout data processing. You are advised to use Safari, Chrome or Edge. Firefox is possible but not recommended given that some minor problems can appear in Firefox.

OpenRefine stores and processes all data locally, in a secure and private environment. It runs a local server that will be visible as an dedicated instance of the CLI. Leave open the CLI until you wish to shutdown the server. The server autosaves your work consistently and leaves behind a full history of your work that can be turned back. It does so with url parameters.

## Resources

- [download](https://openrefine.org/)
- [documentation](https://openrefine.org/docs)
- [github repo](https://github.com/OpenRefine/OpenRefine)

## Set-up

Begin by [downloading the file](https://openrefine.org/).

Goto [OpenRefine Documentation](https://openrefine.org/docs/manual/installing)

## Demo

### Create Project

Create a new project from local files (This Computer), online (WebAddresses URLs), Clipboard, Database (RDBMS such as MySQL or PostgreSQL), or even Google Sheets (Google Data).

A variety of formats can be imported:

- comma-separated values (CSV) or text-separated values (TSV)
- Text files
- Fixed-width columns
- JSON
- XML
- OpenDocument spreadsheet (ODS)
- Excel spreadsheet (XLS or XLSX)
- PC-Axis (PX)
- MARC
- RDF data (JSON-LD, N3, N-Triples, Turtle, RDF/XML)
- Wikitext

Data from any source will be loaded into a new project and will be saved as a new file in your workspace directory.

In OpenRefine, you never have to worry about changing and losing the original.

### Open Project

Open existing OpenRefine projects with `Open Project`.

All your projects are here and can be sorted.

`About` is used to edit project metadata.

### Importing

>The best way to collaborate with another person is to export and import projects that save all your changes, so that you can pick up where someone else left off.

This will contain the entire history from the original project.

### Follow Steps to Create Project

```
1. Download ses.csv from the course GitHub site (modules\04-openrefine\ses.csv)
2. Create project/This Computer/Choose Files/[path]/ses.csv
3. Next>>
4. Look at option
5. Create project>>
```

### Exploring and Transforming Data

#### Arrange Columns

#### Follow Steps to Arrange Columns

```
6. Remove column OBJECTID
7. Move these columns to end: add_date, themes.id, class.id, surname, firstname, site_id, location_id
8. Try sorting by 'All/Edit Columns/Reorder' such that we have this order BegDate, lat, lon, SiteCode, municipality, name, class, summary and then remaining columns.
```

#### Data Types

The data types supported are:

- string (one or more text characters)
- number (one or more characters of numbers only)
- boolean (values of “true” or “false”)
- date (ISO-8601-compliant extended format with time in UTC: YYYY-MM-DDTHH:MM:SSZ)

OpenRefine recognizes two further data types as a result of its own processes:

- error
- null

An “error” data type is created when the cell is storing an error generated during a transformation in OpenRefine.

A “null” data type is a special type that means “this cell has no value.” It’s distinct from cells that have values such as “0” or “false”, or cells that look empty but have whitespace in them, or cells that contain empty strings. When you use type(value), it will show you that the cell’s value is “null” and its type is “undefined.” You can opt to show “null” values, by going to All → View → Show/Hide ‘null’ values in cells.

#### Follow Steps to Change Data Types

```
9. Change lat and lon columns to number format by Edit cells/Common Transforms/to Number
10. Change BegDate to Date format by Edit cells/Common Transforms/to Date
```

#### Follow Steps to Create new field like 'site-municipality-state'

Now we want to create a new column that has a more complete site name in the format 'site-municipality-state'. We will first split into parts and the concatenate the parts.

```
11. Split column SiteCode into several columns by separator '-' with 'Edit Column/Split into several columns'.
12. Beginning from municipality column, goto 'Edit column/Join columns. Select and order the columns you want to concatenate. Add a hyphen as a separator.
13. Move the other three columns to the end of the sheet.
```

#### Follow Steps to Apply Facets

Faceting is used for filter data and for pattern searching.

Let's add a facet to the BegDate column:

```
14. BegDate/Facet/Timeline facet
```

With the new visual on left, we can quickly delimit our data to select years.

Let's add a 'state' facet:

```
15. state/Facet/Text facet
```

Now let's 'include' rows only from the states of 'Chiapas', 'Quintana Roo', and 'Yucatán'.

You might want to reset the BegDate facet.

Now let's exclude those from Chiapas.

#### Follow Steps to Cluster and Edit

The 'Cluster' tool is very powerful and allows you to apply various algorithms to your data in order to clean your data. Let's do this with the 'name' column.

```
16. name/Edit cells/Cluster and edit
```

If you find nothing, take off the facet filters by clicking 'reset'.

```
Repeat Step 16, choosing 'drought, seasonal' as the universal value in this cluster. Go to 'merge selected and close'.
17. summary/Edit cells/Cluster and edit. Choose three options and then 'merge selected and close'
```

#### Follow Steps to Transform Data

OpenRefine gives you many ways to clean your data. You will do some of this in your exercises, but at this time, let's look at a few common steps.

```
18. all/edit all columns/Trim leading and trailing whitespace
19. all/edit all columns/Collapse consecutive whitespace
```

### History

>any activity that changes the data can be undone....
>
>The change history of each project is saved with the project's data, so quitting OpenRefine does not erase the steps you've taken.
>
>OpenRefine autosaves your actions every five minutes by default ([about OpenRefine History](https://openrefine.org/docs/manual/running#history-undoredo))

#### Exporting History

You can export your operations to a new project by going to `Undo/Redo` tab and the `Extract`.

### Exporting Your Work

>Once your dataset is ready, you will need to get it out of OpenRefine and into the system of your choice. OpenRefine outputs a number of file formats, can upload your data directly into Google Sheets, and can create or update statements on Wikidata.

Your options are:

- Tab-separated value (TSV) or Comma-separated value (CSV)
- HTML-formatted table
- Excel spreadsheet (XLS or XLSX)
- Open Document Format (ODF) spreadsheet (ODS)
- Upload to Google Sheets (requires Google account authorization)
- Custom tabular exporter
- SQL statement exporter
- Templating exporter, which generates JSON by default

You can also export reconciled data to Wikidata, or export your Wikidata schema for future use with other OpenRefine projects:

- Upload edits to Wikidata
- Export to QuickStatements (version 1)
- Export Wikidata schema

Importantly, you can export your project as a fully readable OpenRefine project that can be imported by another user. It will export as a tar file that can be sent via email or as a Google Drive link. You will use this to submit your work for this lesson.

#### Follow Steps to Export your Project

```
20. Export your project and send the file or a link to the file via email to bskopyk@binghamton.edu.
```
