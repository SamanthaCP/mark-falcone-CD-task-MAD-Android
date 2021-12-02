# Curriculum Developer Paid Task: Lab Rewrite

**Contents**

- [Curriculum Developer Paid Task: Lab Rewrite](#curriculum-developer-paid-task-lab-rewrite)
  - [Overview](#overview)
    - [Lab Details](#lab-details)
    - [Evaluations Criteria](#evaluations-criteria)
  - [About this Repository](#about-this-repository)
    - [Structure of Repository](#structure-of-repository)
  - [Deliverables](#deliverables)
    - [Preparing your Deliverables](#preparing-your-deliverables)
    - [Guidelines](#guidelines)

## Overview

If you are reading this, you are a candidate for the [CodePath Curriculum Developer](https://jobs.codepath.org/o/curriculum-developer) position. The next step in the process is to complete a paid project. We’re excited for the opportunity to see how you think about and create curricula. We believe high-quality curriculum materials are instrumental in ensuring that our courses live up to their transformational promise to students, and we are here to support you as you embark on this task.

You should have already received details of the scope of the paid task in the [Curriculum Developer Interview Task Google Doc](blank.com).

### Lab Details

In this section we want you to choose to update an existing lab from the **Mobile App Development Android** course. In this portion of the lab we want to give you the opportunity to replace one of our existing labs. Be sure to also incorporate your analysis and recommendations from auditing our first two weeks of the curriculum in your rewrite.

The Flashcard App is divided into 4 total labs.  Each lab focuses on a specific feature to elevate the app’s functionality. You may choose to focus on updating a single lab at any point in the course. This means that you could rewrite the first part of the lab in week 2 or rewrite the lab in week 7. You may also choose to go in a different direction and change the entire project focus.

* **Week 2:** Creating a new App
* **Week 4:** Creating Cards
* **Week 5:** Saving Data
* **Week 7:** Animations and Styling

In the existing labs below you may notice that some instructions are provided via video walkthroughs. We would like your rewrite to feature instructions mainly in a written format. Keep in mind that we would like to provide students with both written and video format when released into production. We highly encourage you to consider how your written instructions might eventually translate to video instructions.

### Evaluations Criteria

We ask that you complete your revisions in GitHub because in addition to reviewing your curriculum development work we will also be evaluating your ability to:

* navigate, manage, and edit on GitHub using git and markdown.
* create a branch using git commands and explain the purpose and importance of version control.
* understand how pull requests track changes and implement best practices for code reviews on GitHub.

**GitHub Tip:** *Do not clump all of your changes into one commit. When making changes to the lab it is best to break up changes into small multiple commits. This most mimics our production workflow and also allows you to revert to an older version if you face any issues with your latest change.*

## About this Repository

This repository is a template for how you will provide and submit you deliverables.  At CodePath we use GitHub and markdown as the main source all of our curriculum content. The courses system supports blended learning courses of nearly any topic and in multiple different formats. The courses system was designed with the following features:

* Github-centric authentication process for students
* Content is all formatted in markdown for easy management
* Built-in viewing of common files such as PDFs
* Built-in of video files (sourced through Vimeo or Youtube)
* Easy way to link pages, files, and images within other content
* Fast and easy to use with a unit-centric course design
* The primary guideline being to make building courses similar to building open-source software. This is now being used by participants for all of our courses but is still forever a work in progress.

### Structure of Repository

These directories are processed and used to render a course to the students participating in a course. Each content directory (i.e modules) contains either text files or media content (images, slides). For example, the "overviews" folder looks like:

<a href="https://github.com/codepath/university_courses_content/tree/master/android_university/overviews" target="_blank"><img src="https://i.imgur.com/6V9DGfG.png" width="700" /></a>

Each text file is created using [markdown](https://daringfireball.net/projects/markdown/syntax) for text formatting. Here's a [markdown cheatsheet](http://support.mashery.com/docs/read/customizing_your_portal/Markdown_Cheat_Sheet) with more details. Each file within represents a "unit" of the course. For example, the first unit labelled as `overview_1.md` shown in the first week of class renders as:

<a href="https://github.com/codepath/university_courses_content/blob/master/android_university/overviews/overview_1.md" target="_blank"><img src="https://i.imgur.com/TkfExhI.png" width="700" /></a>

Each unit is then represented on a different page and students can navigate between units (weeks of the course) through the left sidebar. The system knows which week the student is currently on and displays the tabbed sections for that unit by default.

## Deliverables

1. Written proposal including the changes you would like to make to the lab. This write-up can be in a google doc/sheet or [hackmd](https://hackmd.io/) or in whichever document format you prefer. The audience for this document should be to a CodePath curriculum manager. The goal of this proposal is for you to articulate the rationale behind your modifications and convince your audience that this rewrite is essential to elevating the quality of our curriculum.
  We expect your proposal to include the following:

  * **Overview of the changes.** In a brief paragraph, describe the high-level changes to that you will be implementing
  * **Rationale and impact.** Why are these changes necessary? Was there feedback that you have analyzed that contributed to this decision? How will this impact our students and facilitators?
  * **General Timeline.** Provide an estimated timeline on how long it would take a single developer to implement these changes. They do not need to be exact times, you can place ranges. In general, we would include timelines for 1st draft, review, 2nd draft, and final QA.

2. **Write-up of lab.** The lab write-up document should be student-facing, and should include:
	* **Overview of the Lab**
		* Brief description of the lab
		* Learning Objectives/Goals
		* A list of prerequisite skills/knowledge
		* A list of resources
		* A list of core and stretch features (if applicable)
	* **Starter code and/or exemplar code** (if applicable)
	* **Student-facing written instructions** to breakdown the steps of the lab.
	* **Index of topic guides/resources** you would have created and linked in the lab.
		
		***Note:*** Topic guides are more detailed pages on a specific topic or tool. In some cases, labs might remind students of high-level details of a topic covered by a facilitator (instructor, tech fellow, or professor) but fail to go into specifics. This is where a topic guide would be created to provide more detail on a topic, similar to a section in a guiding textbook. 
	* **(Stretch goal) Link to a relevant topic guide which you actually wrote up.** *Note: this is not required! A description of topic guides you would include alongside the lab is sufficient.*
	* **Instructor resources and solutions.** Include in the lab facilitation notes for an instructor or teaching assistant that highlights potential challenges students might encounter. This may be in the form of highlighting common mistakes, solutions to challenges, tips to prepare for the lab, etc.

### Preparing your Deliverables

Please be sure to first read through all of the steps below before beginning this task.

1. **Familiarize yourself with GitHub workflows and how to make changes.**
	1. You can edit files using the [GitHub browser](https://github.com/), [GitHub Desktop](https://desktop.github.com/), or an IDE. We recommend using an IDE like [VS Code](https://code.visualstudio.com/) for larger changes. 
	1. Be comfortable using git for version control. You should know how to clone, push, pull, commit, and branch using git. Read the GitHub Docs to learn more [about git](https://docs.github.com/en/get-started/using-git/about-git).
1. **Read through the README.md file.** This file will contain information about how the course files are structured with respect to our online course portal ([courses.codepath.org](https://courses.codepath.org)). In this course repo you will have access to all labs (weeks 2, 4, 5, and 7) in the Mobile App Development course. We only expect you to make updates to one lab. 
1. **Prepare your branch for changes.** You will **NOT** be making changes to the `main` branch of this repository. Instead you should be **creating your own branch** and committing changes there.
1. **Make changes to your respective lab files. **Remember that you can edit files using the [GitHub browser](https://github.com/), [GitHub Desktop](https://desktop.github.com/), or an IDE. We recommend using an IDE like [VS Code](https://code.visualstudio.com/) for larger changes. We don’t expect you to change all of the files present in the repository. It is okay to keep some components of the existing lab. If you believe parts of it don’t need revision, we don’t expect you to reinvent the wheel! 
1. **Commit and push changes to your branch.** Once you have completed your changes in a single file, be sure to commit and push your changes to your branch. Don’t forget to include a description with your commit so that we can follow your commit history. 
	
	*GitHub Tip: Do not clump all of your changes into one commit. When making changes to the lab it is best to break up changes into small multiple commits. This most mimics our production workflow and also allows you to revert to an older version if you face any issues with your latest change.*
1. 4. **Opening a Pull Request.** Once you are ready to submit your changes to the lab, open a pull request with your branch. This will indicate to us that you are ready to merge your changes to our main branch and therefore ready for review.
   1. Don’t forget to review + proof check your work before submitting! Remember that markdown has very specific syntax rules.
   2. Add  **@SamanthaCP** and **@kellyanguiano** as reviewers to your pull request.
   3. Be sure to add a short description to the changes you have made.



### Guidelines

* It is okay to keep some components of the existing lab. If you believe parts of it don’t need revision, we don’t expect you to reinvent the wheel!
* Be as creative as possible, and think about how to make the lab fun for students
* Be sure to incorporate any of your relevant recommendations from the first part of the task. 
