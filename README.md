# eViewer Page Manipulations Sample

The **eViewer Page Manipulations Sample** is a client-side web
application that demonstrates powerful page-level editing capabilities
within eViewer. This sample enables users to reorganize documents
effortlessly by cutting, copying, pasting, and deleting pages, making
document restructuring simple and intuitive. The sample works
independently without relying on any backend services or external
integrations.

With this sample, users can easily select one or more pages and perform
essential manipulation actions to create a refined and well-organized
document. These interactions help streamline workflows such as preparing
reports, removing unnecessary pages, or duplicating important content.
The seamless page manipulation features enhance user productivity and
offer an efficient way to edit documents directly within the viewer.

## Set up eViewer v7

Follow the steps below to run the eViewer Page Manipulations Sample:

1.  Clone this repository and host it via an HTTP server.

2.  Download the viewer static files from the [eViewer7 npm
    repo](mailto:(https://www.npmjs.com/package/@mstechusa/eviewer7))
    into the **viewer** folder. All viewer files should be placed in the
    root viewer folder.
	
3.  Open **eViewerPage.html** in your browser to launch the viewer.

## Using Page Manipulations in eViewer

Follow the steps below to explore and use the page manipulation features
effectively:

1.  Launch the eViewer application and open a document you want to
    modify.
2.  The viewer interface loads the document along with the **Page
    Editing Tools** located in the top toolbar.
3.  Choose the desired action- **Cut**, **Copy**, **Paste**, or
    **Delete**.
4.  Select a page in the thumbnail panel to perform the operation.
5.  For **Cut** or **Copy**, the selected page is stored temporarily for
    later use and can be inserted elsewhere using **Paste**.
6.  **Delete Page** permanently removes the selected page from the
    document.
7.  After each action, a confirmation message appears to confirm
    successful execution.

## Page Manipulations via APIs

Page-level operations can also be executed programmatically using
eViewer's **Page Manipulation APIs**. The top section of the interface
includes buttons connected directly to these APIs, showing how
developers can automate editing actions.

These buttons trigger respective API-driven operations:

-   [`Cut Page`](https://eviewer.net/developer-guide/#Cut_Page) - Removes the currently selected page and stores it
    temporarily.
-   [`Copy Page`](https://eviewer.net/developer-guide/#Copy_Page) - Duplicates the selected page programmatically for
    later pasting.
-   [`Paste Page`](https://eviewer.net/developer-guide/#Paste_Page) - Inserts the previously cut or copied page at the
    desired position.
-   [`Delete Page`](https://eviewer.net/developer-guide/#Delete_Page) - Permanently deletes the selected page using the
    API.
![](
https://eviewer.net/wp-content/uploads/2025/11/Page-manipulations.png)


For complete API documentation, method details, and examples, visit:\
**https://eviewer.net/developer-guide/**

## API Implementation Code

Below are JavaScript examples demonstrating how to perform page
manipulation actions programmatically:

``` javascript
function cutPage() {
  eViewerObj.editingService.cutPage().then((response) => {
    console.log("cutPage: " + response);
  });
}
```

``` javascript
function copyPage() {
  eViewerObj.editingService.copyPage().then((response) => {
    console.log("copyPage: " + response);
  });
}
```

``` javascript
function pastePage() {
  eViewerObj.editingService.pastePage().then((response) => {
    eViewerObj.documentService.getCurrentPage().then((currentPage) => {
      console.log("currentPage After pastePage: ");
      console.info(currentPage);
    });
    console.log("pastePage: " + response);
  });
}
```

``` javascript
function deletePage() {
  eViewerObj.editingService.deletePage().then((response) => {
    eViewerObj.documentService.getCurrentPage().then((currentPage) => {
      console.log("currentPage After detetePage: ");
      console.info(currentPage);
    });
    console.log("deletePage: " + response);
  });
}
```

## Try the Demo

Experience the live version of this sample here:

[**Live Demo**](https://mst2019b2.eastus.cloudapp.azure.com:8443/eviewer7-page-manipulation)

## License

The license key is provided by **MST**.

For licensing inquiries or more information, contact:\
**info@ms-technology.com**
