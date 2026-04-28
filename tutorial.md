<!--
author:   Martin Zurowietz
email:    m.zurowietz@uni-bielefeld.de
version:  1.0.0
language: en
narrator: US English Female
comment:  An open educational resource introducing the BIIGLE image and video annotation platform.
-->

# BIIGLE for Beginners

**BIIGLE** is a free, web-based platform for annotating images and videos from scientific surveys. Applications range from marine imagery by remotely operated vehicles, drop cameras, or autonomous underwater vehicles to terrestrial imagery and microscopy.

This tutorial teaches the complete beginner workflow: from creating a user account, through setting up projects and annotating data, to exporting the results. Each chapter introduces one concept, then gives you a hands-on task to solve on [biigle.de](https://biigle.de).

Sample data is provided for the tasks. You may also use your own images and videos if you prefer. Supported image formats are JPEG, PNG, WebP and TIFF. Supported video formats are MP4 (H.264 and H.265/HEVC) and WebM (VP8, VP9, AV1).

> This tutorial targets the public instance at [biigle.de](https://biigle.de). If you use a self-hosted BIIGLE instance, the steps are identical but the URL will differ.

---

## Chapter 1: Introduction to BIIGLE

BIIGLE is a software for image and video annotation. This chapter defines the term "image annotation" and shows a summary of the remaining content of this tutorial.

### What is image annotation?

An image annotation records *what* is *where* in an image. It combines two pieces of information:

- a **marker**: a shape drawn on the image (e.g. a point, rectangle, circle, polygon, ...)
- a **label**: a name or category assigned to that marker (e.g., "Fish", "Coral", "Tree")

Scientific imaging surveys routinely produce tens of thousands of images and hours of video footage. Annotating these manually runs into a fundamental trade-off of whether the data is annotated fast, accurately or complete:

- **fast**: annotation finishes within the time budget of the research project
- **accurate**: every annotation is correct and reproducible
- **complete**: every object of interest is annotated

In most cases, you can only achieve *two* of these at once.

> **BIIGLE's mission**
>
> Annotation should be accurate and fast, while remaining sufficiently complete for scientific decision-making.

### What you will learn

| Chapter | Topic |
|---------|-------|
| 2 | Signing up and the dashboard |
| 3 | Projects, volumes, users, and roles |
| 4 | Label trees (your annotation vocabulary) |
| 5 | Creating image and video volumes |
| 6 | Annotating images |
| 7 | Annotating videos |
| 8 | Exporting reports |

### Quiz

Which of the following are **not** part of an image annotation?

- [[ ]] A shape drawn on the image
- [[X]] The date and time when the image was taken
- [[ ]] A label that classifies the shape
- [[X]] A screenshot of the image region marked by the shape
***
An image annotation consists only of a shape and a label. Image metadata is recorded separately and screenshots can be derived from the image and the annotation later.
***

---

## Chapter 2: Sign Up and Log In

BIIGLE is a web-based application which means that it does not run on your own computer but is accessed remotely through a web browser. Each user has to create a user account so BIIGLE can tell them apart. This chapter explains how to create your user account so you can access BIIGLE.

### Creating an account

To create a user account go to [biigle.de](https://biigle.de) and click **Sign up**. You can either use a federated user account via Life Science Login (supports European institutes and universities as well as ORCID, Google and more) or NFDI Login (supports German institutes) or create a dedicated user account by clicking on "use your personal email address". There, fill in your email, name, affiliation, and password and click on "Sign up".

> New accounts on biigle.de need to be approved by a BIIGLE admin before they can access all features (e.g. upload data or create projects and label trees). Approval usually takes no more than one business day.

Once you are logged in, you land on your **dashboard**. This is the starting point for everything you do in BIIGLE: it lists your projects, volumes, and recent activity.

### Task

Create a BIIGLE account at [biigle.de](https://biigle.de) and open the dashboard.

<details>
<summary>Solution</summary>

1. Navigate to [biigle.de](https://biigle.de/register).
2. Choose Life Science Login, NFDI Login or "use your personal email".
3. Authorize the account or fill and submit the sign up form.
4. Wait for BIIGLE admin approval (you will receive an email).
5. Return to [biigle.de](https://biigle.de) and log in.

</details>

---

## Chapter 3: Organizing Data

BIIGLE supports image and video annotation of large datasets in a collaborative way. This chapter introduces the data hierarchy of BIIGLE and the building blocks that are important for data organization and collaboration.

### The three-level hierarchy

Your work in BIIGLE is organized in three nested levels. We start from the bottom:

1. An **image or video** is the file that you uploaded or linked to BIIGLE. This is what you want to annotate.
2. A **volume** is a collection of images or videos that belong together, similar to a directory on your computer. A volume can contain either images or videos but not both.
3. A **project** is the top-level container. It groups volumes and controls which users have access to them.

In addition to files, volumes and projects, there are also **label trees**. These are collections of labels that can be used for annotation. Label trees are managed separately to projects. A single label tree can be attached to, and reused, across many different projects.

### Project member roles

Every user in a project has one of four roles:

| Role | Permissions |
|------|-------------|
| **Guest** | View-only: can see volumes, files, and annotations |
| **Editor** | Can create, edit, and delete *their own* annotations |
| **Expert** | Can create, edit, and delete annotations of *any* user of the project |
| **Admin** | Full control: can manage members, volumes, label trees, project settings |

The user who creates a project is automatically its admin.

### Quiz

True or false: you can mix images and videos in the same volume.

- [( )] True
- [(X)] False
***
A volume can contain only images or videos but not both.
***

Which role is recommended for a PhD student who actively annotates but should not overwrite their colleagues' work?

- [( )] Guest
- [(X)] Editor
- [( )] Expert
- [( )] Admin
***
A project editor can create and modify their own annotations but cannot delete the annotations of other users.
***

### Task

Create a new project on [biigle.de](https://biigle.de) with a name and short description.

<details>
<summary>Solution</summary>

1. On the dashboard, click on the **Create Project** button.
2. Enter a **name** (e.g., "My First Project") and a short **description**.
3. Click **Create**.
4. The project page will automatically open. This is where you manage volumes, label trees, and members.

</details>

---

## Chapter 4: Label Trees

One challenge of data annotation is using common vocabularies for annotation comparison. BIIGLE provides shareable label trees to address this challenge, which are explained in this chapter.

### What is a label tree?

A **label tree** is a collection of labels, either as a flat list or a hierarchical tree. It works like a taxonomy or classification scheme and defines which labels are available for annotation.

A small example:

```
● Echinodermata
├──● Asteroidea
└──● Ophiuroidea
● Chordata
├──● Teleostei
└──● Elasmobranchii
```

Label trees are managed separately to projects. This means one carefully curated label tree can be attached to several projects at once, so that different research projects share the exact same vocabulary.

### Visibility

There are two types of label trees:

- **Public**: These label trees are visible to all BIIGLE users and attachable to any project.
- **Private**: These label trees are only available to users and projects explicitly authorized by the label tree admins.

### Creating a label tree

1. On the dashboard, click on the **Create Label Tree** button.
2. Give the tree a name, optional description, and choose a visibility.
3. The label tree page will automatically open. This is where you manage its labels.
4. To create a label, enter a label name in the input on the right and click on the **+** button.
5. To create a child label, select the parent label in the list on the left, then enter the label name and click the **+** button on the right.

### Attaching a label tree to a project

A label tree must be attached to your project before its labels can be used for annotation.

1. Open your project page.
2. Select the **Label Trees** tab at the top.
3. Enter the name of the label tree in the **Attach a Label Tree** input and press <kbd>Enter</kbd> to attach the label tree.

> You will only find public label trees or private label trees that previously authorized your project in the attach label tree input.

As a shortcut, you can also click on the **Create Label Tree** button in the Label Trees tab of your project. The new label tree will be immediately attached to your project, even if it is private.

### Task

Create a label tree with at least 5 labels organized in at least two levels of hierarchy and attach it to your project.

<details>
<summary>Solution</summary>

1. Open the **Label Trees** tab of your project.
2. Click on the **Create Label Tree** button on the right.
3. Enter a name, choose the visibility, enter a short description and confirm.
4. The new label tree page will open. In the **New label** form on the right, enter a label name and click on the **+** button to confirm.
5. Click that label on the left to select it, then create two child labels.
6. Unselect the parent label with a click and add another top-level label and one or two children.
7. Return to your project, open the **Label Trees** section. The label tree should be attached to your project.

</details>

---

## Chapter 5: Creating a Volume

This chapter introduces the volume as the fundamental building block for a dataset in BIIGLE.

### What is a volume?

A volume is a named collection of either images or videos. You can think of a volume as a directory of files on your computer. A volume typically includes e.g. all images of one particular transect or videos of one ROV dive.

Each volume belongs to a project and the project overview page lists all of its volumes. A click on a volume thumbnail opens the volume overview where you can browse thumbnails of all images or videos that belong to this volume.

### Where do the files come from?

Since BIIGLE is a web application, it cannot read files directly from your computer. The files must be provided in a way that can be accessed by the BIIGLE server.

BIIGLE supports three different sources for files:

- **Storage Request**: Files are uploaded from your computer to the BIIGLE server. Each upload is called a Storage Request which is reviewed by the BIIGLE admins before the files can be used for a new volume. This is the simplest option and recommended for this tutorial.
- **Remote Location**: You set up a public web server that BIIGLE can query to access the files. The files stay under your control but the setup is more complicated and files can be accessed by anyone who knows the address of the server.
- **Storage Disks**: You set up storage with a cloud provider and authorize BIIGLE to access it. The files stay under your control and access is secure but cloud storage and data transfer cost can become expensive for large datasets.

### Uploading files

Files for a new volume can be uploaded as a Storage Request in BIIGLE.

1. Visit the dashboard and click on the **Upload Files** button.
2. Create at least one (virtual) directory to organize the files of the storage request by clicking on the **Add directory** button and entering a directory name.
3. Click on the **Add files** button to choose files from your computer that should be added to the new directory of the storage request.
4. Once you have created all directories and selected all files, click the **Submit** button to start the upload.
5. When the upload is complete, the storage request is automatically submitted for review by the BIIGLE admins.
6. You receive a notification email if the storage request was approved or rejected.

You can create multiple directories and subdirectories to organize files in the storage request. You can also submit multiple storage requests for different directories. Files uploaded in different storage requests but to the same directory will be merged in your personal storage.

> To avoid accumulating unused files, storage requests and their uploaded files are automatically deleted from the BIIGLE server after 12 months. You will receive a warning email a few weeks before expiration. Then, you also have the chance to extend the storage request for another 12 months if you still need the files for annotation.
>
> Volumes using uploaded files are never automatically deleted. If an uploaded file no longer exists, the image or video annotation tool will stop working. You can still access the volume and download annotation data as reports.

### Task

Create a storage request and upload files for a new volume. You can use your own files or the provided sample data.

Sample data: `TODO link to download page`

<details>
<summary>Solution</summary>

1. Optional: Download the sample data from the link above.
2. Visit the dashboard and click on the **Upload Files** button.
3. Create a (virtual) directory to organize the files of the storage request by clicking on the **Add directory** button and entering the directory name.
4. Click on the **Add files** button to choose files from your computer that should be added to the new directory of the storage request.
5. Click the **Submit** button to start the upload. Wait for the upload to finish.
6. Wait for BIIGLE admin approval of the storage request (you will receive an email).
</details>

### Creating the volume

Once you have uploaded files and the storage request was approved (or you have set up a remote location or storage disk), you can go ahead and create the volume.

1. Open your project page and click **Create Volume**.
2. Choose if you want to create an image volume or a video volume and click **Continue**.
3. Enter a volume name and choose **Uploaded files** as file source.
4. In the file browser, click on a directory or on individual files (multiple files can be selected with <kbd>Ctrl</kbd>+Click) to select them for the volume.
5. Click **Create**.

You will be immediately forwarded to the new volume page. It may take a few seconds until BIIGLE has generated the image thumbnails for the volume overview. Refresh the page to see them.

### Task

Create one image volume and one video volume in your project using the provided sample files (or your own). Verify that thumbnails appear in the volume overview.

<details>
<summary>Solution</summary>

1. Open your project page and click **Create Volume**.
2. Select the "image volume" type and click **Continue**.
3. Enter a volume name and choose **Uploaded files** as file source.
4. In the file browser, click on the directory of uploaded files to select them for the volume.
5. Click **Create**.
6. Refresh the page after a few seconds to see the file thumbnails.
7. Repeat with the "video volume" type.

</details>

### Quiz

A storage request and its uploaded files are automatically deleted:

- [( )] after 6 months
- [(X)] after 12 months
- [( )] never
***
A storage request and its uploaded files are deleted after 12 months unless the storage request is manually extended before it expires. Volumes and annotation are never automatically deleted.
***

---

## Chapter 6: Annotating Images

The most important features of BIIGLE are the image and video annotation tools. Both work fundamentally in the same way but have subtle differences. This chapter first introduces the image annotation tool.

### Opening the image annotation tool

From the volume overview, click any image thumbnail to open the image annotation tool. The image annotation tool consists of two sections, the image and the sidebar.

TODO: screenshot with annotated sections and toolbar

<section>

#### The image

The image can be zoomed and panned, similar to what you may be used to from an interactive map. On the top right there is a minimap, showing the full image as well as an indicator of your current viewport. On the top left there are buttons to zoom the image to the full resolution or to fit it to your browser window.

At the bottom of the image there is a toolbar with buttons for navigation and annotation. Use the left/right arrow buttons to navigate to the previous/next image of the volume. The remaining buttons allow you to draw annotations with various shapes or to modify existing annotations.

</section>

<section>

#### The sidebar

The sidebar on the right gives access to tools and context that you may need while annotating. From top to bottom the tabs are:

- **Annotations**: This is a list of all annotations on the image. Click on an item in the list to select and highlight the annotation. here you can also see who has created the annotation.
- **Label Trees**: This tab shows a list of all label trees that are available in the volume. Here you can select the label that you want to use for the next annotation. BIIGLE offers some advanced features such as favourite labels or LabelBOT to speed up the label selection during annotation. Take a look at [the manual](https://biigle.de/manual) if you are curious.
- **Annotation Modes**: Annotation modes allow you to step through the images of a volume in a well-defined way. For example, lawnmower mode lets you systematically scan the images at a fixed zoom level or random sampling automatically creates point annotations so you only have to choose their labels.
- **Image Labels**: Sometimes you want to attach a label to the whole image (e.g. if it has "bad quality"). This tab lists all existing image labels and allows you to attach new ones.
- **Color Adjustment**: Here you can adjust brightness, contrast, gamma, etc. to make faint objects more visible.
- **Settings**: This tab offers various toggles and options to customize the annotation tool to your needs. You also find a button to show all available keyboard shortcuts here.

</section>

### Creating an annotation

The workflow to create a new annotation is always the same sequence: select the label, select the shape, then draw:

1. Open the label trees tab and click a label. The currently selected label is indicated at the bottom-right of the image area so you see it even if the sidebar is closed.
2. Select a shape from the toolbar at the bottom of the image.
3. Draw the annotation on the image.

### Annotation shapes

TODO: Add icons for shapes

| Shape | How to draw |
|-------|-------------|
| **Point** | One click on the target. |
| **Rectangle** | The two first clicks mark the main axis of the object. The third click defines the width of the rotated rectangle. There is also an option for aligned rectangles that can be drawn with two clicks. |
| **Circle** | The first click defines the center and the second click the radius of the circle. |
| **Line string** | Start the line with a click. Each subsequent click extends the line. A double-click finishes the line. |
| **Polygon** | Start the polygon with a click. Subsequent clicks add points to the polygon. A double-click finishes the polygon. |

There are also more advanced annotation shapes and tools available. Explore the buttons and [the manual](https://biigle.de/manual) if you are curious.

### Editing and deleting annotations

There are several ways to edit an existing annotation:

- **Modify shape**: Hover over a vertex of an annotation to reveal a handle, then drag it to update the annotation.
- **Attach label**: Activate the attach label tool and click on an existing annotation to attach an additional label to it.
- **Move annotations**: Activate the move tool, then click an annotation to select it. Now you can drag the annotation to move it.

Selected annotations are deleted by pressing on the **Delete** button in the toolbar or <kbd>Del</kbd>.

### Quiz

In what order must you set things up to create an annotation?

- [( )] Draw the shape, then assign a label
- [(X)] Select a label, then draw the shape
- [( )] It does not matter
***
You have to select the label first and then draw the shape. When the shape is finished, the new annotation is immediately created.
***

Which shape requires the fewest clicks to draw?

- [( )] Rectangle
- [( )] Circle
- [(X)] Point
- [( )] Line string
- [( )] Polygon
***
Points are quickest to draw but beware: Points and line strings cannot be used as training data for modern computer vision models!
***

### Task

Open one of the images of the image volume you created in Chapter 5 in the image annotation tool. Using labels from the label tree you created in Chapter 4, create at least one annotation of each of these shapes: Point, Rectangle, Circle, Polygon.

<details>
<summary>Solution</summary>

1. Open your image volume and click a thumbnail to enter the image annotation tool.
2. Open the **Label Trees** tab in the sidebar on the right and click a label.
3. **Point**: Click the point tool in the bottom toolbar, then click an object.
4. **Rectangle**: Click the rectangle tool, then click the "start" of an object (e.g. the head of a fish), then click the "end" (e.g. the tail) and finally expand the rectangle and click a third time to finish it.
5. **Circle**: Click the circle tool, click the center of an object, then click its edge.
6. **Polygon**: Click the polygon tool, click several vertices around an object, double-click the last vertex to close the shape.
7. Every annotation is saved automatically. Switch to the **Annotations** tab in the sidebar to see them listed.

</details>

---

## Chapter 7: Annotating Videos

The video annotation tool of BIIGLE works mostly similar to the image annotation tool. However, there are some key differences between image and video annotation. The most important difference between an image annotation and a video annotation is that the video annotation can span several frames/seconds of the video. This means that a video annotation can track an object in the video across different positions and video frames. The video annotation tool of BIIGLE is designed to support a workflow of creating both "single-frame" video annotations (marking an object in a still-image frame of the video) and "multi-frame" video annotations (tracking a moving object across multiple video frames).

### Opening the video annotation tool

Just like the image annotation tool, the video annotation tool is opened with a click on the video thumbnail in the video volume overview. In addition to the familiar sections for the video display and the sidebar, the video annotation tool also features a timeline below the video. The timeline allows you to see and manage video annotations across the whole duration of the video. Video annotations are shown in different tracks, one for each label, and can be selected, cut or linked similar to video clips in professional video editing software. Single-frame video annotations are shown as small bars in the timeline. Multi-frame video annotations are shown as long bars, depending on the duration of the annotation. Video playback can be controlled with buttons in the toolbar at the bottom of the video.

TODO: screenshot with annotated sections and toolbar

### Single-frame annotation

A single-frame video annotation is just like an image annotation, it marks an object in a still-image frame of the video. But in addition to the workflow of creating image annotations (select the label, select the shape, then draw), creating a video annotation has an additional final "confirm" step. To create a single-frame video annotation:

1. Pause the video at the desired frame.
2. Select a label.
3. Select a shape.
4. Draw the annotation.
5. Confirm by clicking the [TODO: CHECKMARK_ICON] button or pressing <kbd>Enter</kbd>.

In the timeline, the new annotation appears as a small bar. This way you can easily see what is annotated when in the video.

> If you only create single-frame annotations, there is a handy option "Single-Frame Annotation" in the settings tab. When enabled, video annotations are automatically confirmed when the shape was drawn.

### Multi-frame annotation

A multi-frame video annotation can track a moving object across multiple video frames. This is also the reason why creating video annotations requires an additional "confirm" step. The shape of a multi-frame annotation is drawn multiple times at different "keyframes". To create a multi-frame video annotation:

1. Pause the video at the first frame where the object appears.
2. Select a label.
3. Select a shape.
4. Draw the annotation. Don't confirm, yet.
5. Play the video and pause at a subsequent frame.
6. Redraw the shape at the object's new position. This creates a new keyframe for the annotation.
7. Repeat for as many keyframes as you need.
8. Confirm by clicking the [TODO: CHECKMARK_ICON] button or pressing <kbd>Enter</kbd>.

In the timeline, the new annotation appears as a long bar spanning from the first to the last keyframe. Different to single-frame annotations, multi-frame annotations are visible as moving shapes when the video is played.

> If you create lots of multi-frame annotations, check out BIIGLE's automatic object tracking in [the manual](https://biigle.de/manual/tutorials/videos/creating-video-annotations).

### Task

Open one of the images of the video volume you created in Chapter 5 in the video annotation tool. Using labels from the label tree you created in Chapter 4, create:

1. One single-frame annotation of a visible object.
2. One multi-frame annotation that tracks a moving object across multiple keyframes.

<details>
<summary>Solution</summary>

**Single-keyframe annotation:**

1. Open the volume and click the video thumbnail.
2. Play the video and pause it where an object is clearly visible.
3. Select a label in the sidebar.
4. Select a shape tool (e.g., circle) in the toolbar at the bottom of the video.
5. Draw the annotation.
6. Press <kbd>Enter</kbd> to confirm the annotation.

**Multi-frame annotation:**

1. Open the volume and click the video thumbnail.
2. Play the video and pause at a frame where a moving object first appears.
3. Select a label in the sidebar.
4. Select a shape tool (e.g., circle) in the toolbar at the bottom of the video.
5. Draw the annotation.
6. Play the video again and pause after a few frames.
7. Redraw the shape at the object's new position.
8. Repeat at least one more time.
9. Press <kbd>Enter</kbd> to confirm the annotation.

</details>

---

## Chapter 8: Exporting Reports

BIIGLE is an annotation tool and not meant to be a long-term archive for files and annotations. Whenever you finish an annotation project you can download the annotation information as a report for analysis and archival.

### What is a report?

A report is a file generated by BIIGLE that contains information about your annotations. There are several report types (e.g. image annotation report, video annotation report, and more) which determine what kind of information is included and several report variants that determine the format of the report. Here is a selection of available report variants (also see the [full list](https://biigle.de/manual/tutorials/reports/reports-schema)):

| Report | Format | When to use it |
|--------|--------|----------------|
| **Abundance** | XLSX | Label counts per image, useful for ecological analysis |
| **CSV** | CSV | All annotations as rows, good for scripting |
| **Area** | XLSX | Includes annotation dimensions |
| **COCO** | JSON | Can be used to train machine-learning models |

Reports can be generated for single volumes or entire projects.

### Generating a report

1. Open your volume (or project).
2. Click the **Reports** tab of the project overview or the [TODO: REPORT_ICON] button in the volume overview.
3. Select a report type and variant.
4. Click **Request this report**.

You will get a notification email once the generated report is ready for download.

### Task

Generate two reports for your image volume: an Abundance report and a CSV report. Download and open both to inspect the output.

<details>
<summary>Solution</summary>

1. Open your image volume.
2. Click the [TODO: REPORT_ICON] button.
3. Select the Abundance report variant
4. Click **Request this report**.
5. Repeat for the **CSV** variant.
6. Wait for the email notification.
7. Download both files and open them.

</details>

---

## What's Next

Congratulations! You have walked through the complete beginner workflow in BIIGLE:

- signing up and understanding how data is organized,
- creating label trees, projects, and volumes,
- annotating both images and videos,
- exporting your work as reports.

There is a lot more that BIIGLE can do. Topics worth exploring once you are comfortable with the basics:

- **Largo**: batch review of many annotations of the same label at once, perfect for quality control or a two-stage annotation workflow.
- **Magic SAM**: turn a single click into a precise polygon.
- **LabelBOT**: let BIIGLE suggest labels for your new annotations.
- **Annotation sessions**: time-boxed annotation for reproducible studies or teaching.
- **BIIGLE API**: script BIIGLE from the outside, great for custom reports, bulk operations or integration with other software.

### Resources

- [BIIGLE manual](https://biigle.de/manual): the full reference documentation
- [BIIGLE newsletter](https://biigle.de/newsletter): occasional updates on new features
- [BIIGLE on GitHub](https://github.com/biigle): open-source code for self-hosting and development
- [BIIGLE API documentation](https://biigle.de/doc/api/index.html): endpoints and rate limits

Happy annotating!
