# powerbi-vizualizations-textFilter-dsmagic
An improved version of the [Power BI Text Filter visualization originally published by Microsoft](https://github.com/microsoft/PowerBI-visuals-TextFilter), with more customization options available

## setup and dependencies
* node.js LTS (latest stable release), this visual was tested and built with [node v16.13.2](https://nodejs.org/download/release/v16.13.2/)
* pbviz should be installed globally `npm i -g powerbi-visuals-tools`
* you must [create and install a certificate for pbviz](https://docs.microsoft.com/en-us/power-bi/developer/visuals/environment-setup?tabs=windows#create-and-install-a-certificate) `pbiviz --install-cert` 
* note: you may need to manually install the generated certifacte
* You must install the following additional development libraries in the build/project folder
  * D3 JavaScript library `npm i d3@^5.0.0 --save`
  * TypeScript definitions `npm i @types/d3@^5.0/0 --save`
  * core-js `npm i core-js@3.2.1 --save`
  * powerbi-visual-api `npm i powerbi-visual-api --save-dev`

## build details
* the visual's unique guid is the same as Microsoft's Text Filter visual, but with the last two characters changed to "DS"
* the `supportsSynchronizingFilterState` capability has been enabled, allowing you to let the filter apply accross multiple tabs in Power BI
* the following customization options have been enabled for the visual (changed `style\visual.less`, `src\settings.ts`, and `src\visual.ts`)
  * the background color of the textbox can be toggled on or off
  * the background color of the textbox can be set to a specific color
* the following style changes were implemented:
  * the background color of the textbox and its inline search button has been set to show the visual's background color through 40% transparent white
  * the background color of the clear button to the right of the textbox
* the following property changes were made in `\pbiviz.json`:
  * displayName = `Text Filter DS`
  * guid = `textFilter25A4896A83E0487089E2B90C9AE57CDS`
  * description = `Daniel Schauer's version of MS Text Filter. Provides a search box that can be placed anywhere in your dashboard. This adds a text filtering capability for quick searching across your data.`
* **the visual was built by** navigating to the project folder, the running the package command via powershell `pbiviz package`

## How to Use It
* Download the `src\textFilter25A4896A83E0487089E2B90C9AE57CDS.1.2.1.pbiviz` file
* Import the visual to Microsoft Power BI Desktop
