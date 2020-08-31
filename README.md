<!-- ⚠️ This README has been generated from the file(s) "blueprint.md" link - https://github.com/andreasbm/readme ⚠️--><p align="center">
  <img src="https://mir-s3-cdn-cf.behance.net/project_modules/disp/a685e7437236.5600962f5b4c4.jpg" alt="Logo" width="150" height="150" />
</p>
<h1 align="center">XML to PDF</h1>
 <p align="center">
		<a href="https://github.com/Gkemon/XML-to-PDF-generator"><img alt="Maintained" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" height="20"/></a>
	<a href="https://github.com/Gkemon/XML-to-PDF-generator"><img alt="Maintained" src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" height="20"/></a>
	</p>

<p align="center">
  <b>Automatically generate PDF file from XML file or Java's View object in Android</b></br>
  <p align="center"> Make PDF from Android layout resourses (e.g - ```R.layout.myLayout```,```R.id.viewID```), Java's view ids or directly views objects <p>
</p>

<br />


<p align="center">
  <!-- GIF <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/demo.gif" alt="Demo" width="800" /> --!>
</p>

* **Simple**: Extremely simple to use. For using <b>Step Builder Design Patten</b> undernath,here IDE greatly helps developers to complete the steps for creating a PDF from XMLs.
* **Powerful**: Customize almost everything.
* **Transparent**: It shows logs,success-responses, failure-responses , that's why developer will nofity any event inside the process. 

<details>
<summary>📖 Table of Contents</summary>
<br />

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#table-of-contents)

## ➤ Table of Contents

* [➤ Installation](#-installation)
* [➤ Getting Started](#-getting-started)
* [➤ License](#-license-1)
</details>


[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#installation)

## ➤ Installation

**Step 1**. Add the JitPack repository to your root ```build.gradle``` at the end of repositories
```
allprojects {
    repositories {
        // ...
        maven { url 'https://jitpack.io' }
    }
}
```

**Step 2**. Add the dependency
```
dependencies {
        implementation 'com.github.Gkemon:XML-to-PDF-generator:1.0'
}
```	
[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#getting-started-quick)



## ➤ Getting Started

You can generate PDF from many sources.
* Layout resources (i.e: ```R.layout.myLayout```)
* View ids (i.e: ```R.id.viewID```)
* Java view objects (i.e ```View```,```TextView```,```LinearLayout```)



###From layout resources:


```java
 PdfGenerator.getBuilder()
                        .setContext(MainActivity.this)
                        .fromLayoutXMLSource()
                        .fromLayoutXML(R.layout.layout_print,R.layout.layout_print)
			/* "fromLayoutXML()" takes array of layout resources.
			 * You can also invoke "fromLayoutXMLList()" method here which takes List of layout resources instead of array. */
                        .setDefaultPageSize(PdfGenerator.PageSize.A4)
			/* It takes default page size like A4,A5. You can also set custom page size in pixel
			 * by calling ".setCustomPageSize(int widthInPX, int heightInPX)" here. */
                        .setFileName("Test-PDF")
			/* It is file name */
                        .setFolderName("FolderA/FolderB/FolderC")
			/* It is folder name. If you set the folder name like this pattern (FolderA/FolderB/FolderC), then
			 * FolderA creates first.Then FolderB inside FolderB and also FolderC inside the FolderB and finally
			 * the pdf file named "Test-PDF.pdf" will be store inside the FolderB. */
                        .openPDFafterGeneration(true)
			/* It true then the generated pdf will be shown after generated. */
                        .build(new PdfGeneratorListener() {
                            @Override
                            public void onFailure(FailureResponse failureResponse) {
                                super.onFailure(failureResponse);
				/* If pdf is not generated by an error then you will findout the reason behind it
				 * from this FailureResponse. */
                            }

                            @Override
                            public void showLog(String log) {
                                super.showLog(log);
				/*It shows logs of events inside the pdf generation process*/ 
                            }

                            @Override
                            public void onSuccess(SuccessResponse response) {
                                super.onSuccess(response);
				/* If PDF is generated successfully then you will find SuccessResponse 
				 * which holds the PdfDocument,File and path (where generated pdf is stored)*/
				
                            }
                        });
```

### Configuration

To configure this library you'll need to create a `blueprint.json` file. This file is the configuration for the templates we are going to take a look at in the next section. If you want to interpolate values from the configuration file into your README file you can simply reference them without a scope. Eg. if you have the field "link" in your `blueprint.json` you can write `{{ link }}` to reference it.

Great. Now that we have the basics covered, let's continue and see how you can use templates!

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#templates)


### Logo

The logo template adds a logo to your readme and looks like this:

<p align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/logo-shadow.png" alt="Logo" width="150" height="150" />
</p>

Use the placeholder `{{ template:logo }}` to stamp it. You will need to add the `logo` field to your `blueprint.json`. The logo field requires an `src` field. Optionally you can provide values for `width`, `height` and `alt`. Below is an example on how to add the data for the logo template.

```json
{
  "logo": {
    "src": "https://raw.githubusercontent.com/andreasbm/readme/master/assets/logo-shadow.png",
    "width": "150"
  }
}
```



## ➤ Contributors
	

| [<img alt="Andreas Mehlsen" src="https://avatars1.githubusercontent.com/u/6267397?s=460&v=4" width="100">](https://twitter.com/andreasmehlsen) | [<img alt="You?" src="https://joeschmoe.io/api/v1/random" width="100">](https://github.com/andreasbm/readme/blob/master/CONTRIBUTING.md) |
|:--------------------------------------------------:|:--------------------------------------------------:|
| [Andreas Mehlsen](https://twitter.com/andreasmehlsen) | [You?](https://github.com/andreasbm/readme/blob/master/CONTRIBUTING.md) |
| 🔥                                               |                                                  |


Use the `{{ template:contributors }}` placeholder to stamp it. Let's sa To use this template your are required to add the `contributors` array to your `package.json` file like this. Only the `name` field is required.

```json
{
  "contributors": [
    {
      "name": "Andreas Mehlsen",
      "email": "hello@example.com",
      "url": "https://twitter.com/andreasmehlsen",
      "img": "https://avatars1.githubusercontent.com/u/6267397?s=460&v=4",
      "info": [
        "🔥"
      ]
    },
    {
      "name": "You?",
      "img": "https://joeschmoe.io/api/v1/random",
      "url": "https://github.com/andreasbm/readme/blob/master/CONTRIBUTING.md"
    }
  ]
}
```

Take note of the `info` array. That one is really exciting! Here you can add lines describing the contributors - for example the role of accomplishments. Take a look [here](https://allcontributors.org/docs/en/emoji-key) for more inspiration of what you could put into the info array.

### License

The license template adds a license section and looks like this:


[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#license)


