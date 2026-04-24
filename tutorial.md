<!--
author:   Martin Zurowietz
email:    m.zurowietz@uni-bielefeld.de
version:  1.0.0
language: en
narrator: US English Female
comment:  An open educational resource introducing the BIIGLE image and video annotation platform.
-->

# BIIGLE for Beginners

**BIIGLE** (Bio-Image Indexing and Graphical Labeling Environment) is a free, web-based platform for annotating images and videos from scientific surveys. Applications range from marine imagery by remotely operated vehicles, drop cameras, or autonomous underwater vehicles to terrestrial imagery and microscopy.

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

BIIGLE support image and video annotation of large datasets in a collaborative way. This chapter introduces the data hierarchy of BIIGLE and the building blocks that are important for data organization and collaboration.

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
3. Enter a **name** (e.g., "My First Project") and a short **description**.
4. Click **Create**.
5. The project page will automatically open. This is where you manage volumes, label trees, and members.

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
1. Visit the dashboard and click on the **Upload Files** button.
2. Create a (virtual) directory to organize the files of the storage request by clicking on the **Add directory** button and entering the directory name.
3. Click on the **Add files** button to choose files from your computer that should be added to the new directory of the storage request.
4. Click the **Submit** button to start the upload. Wait for the upload to finish.
5. Wait for BIIGLE admin approval of the storage request (you will receive an email).
</details>

### Creating the volume

Once you have uploaded files and the storage request was approved (or you have set up a remote location or storage disk), you can go ahead and create the volume.

1. Open your project page and click **Create Volume**.
2. Choose if you want to create an image volume or a Video Volume and click **Continue**.
3. Enter a volume name and choose **Uploaded files** as file source.
4. In the file browser, click on a directory or on individual files (multiple files can be selected with <kbd>Ctrl</kbd>+Click) to select them for the volume.
5. Click **Create**.

You will be immediately forwarded to the new volume page. It may take a few seconds until BIIGLE has generated the image thumbnails for the volume overview. Refresh the page to see them.

### Task

Create an image or a video volume in your project using the provided sample files (or your own). Verify that thumbnails appear in the volume overview.

<details>
<summary>Solution</summary>

1. Open your project page and click **Create Volume**.
2. Choose if you want to create an image volume or a video volume and click **Continue**.
3. Enter a volume name and choose **Uploaded files** as file source.
4. In the file browser, click on the directory of uploaded files to select them for the volume.
5. Click **Create**.
6. Refresh the page after a few seconds to see the file thumbnails.

</details>

### Quiz

A storage request and its uploaded files are automatically deleted:

- [( )] After 6 months
- [(X)] After 12 months
- [( )] Never
***
A storage request and its uploaded files are deleted after 12 months unless the storage request is manually extended before it expires.
***
