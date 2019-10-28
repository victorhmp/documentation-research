# Biggest open-source projects in 2018 (GitHub)

Every year, GitHub releases a list of the top open source projects hosted in their platform. They rank projects based on **contributor count**.

Below is a list with the results for 2018:

![list-open-source](https://i.imgur.com/dyPNKHh.png)

We're going to take a look at how these top projects handle their documentation.

## Visual Studio Code or VSCode (by Microsoft)

Visual Studio Code is a text editor (the one I'm using to right this) created and maintained by Microsoft. All of its source code is open-sourced and licenced under the MIT license.

They have a website dedicated to VSCode at: <https://code.visualstudio.com/>. And their documentation center lives at <https://code.visualstudio.com/docs>.

- The whole website is using _React_ (an outdated version, btw).
- The first thing you see is this:

  ![vs-code-docs-home](https://i.imgur.com/Ynxr3Re.png)

  which is an overview section, followed by a gallery of the most used extensions for the editor, a "First Steps" section that contains a list of useful links to get the user up-and-running quickly, three links to resources regarding Keyboard Shortcuts, a link to download VSCode and finally some links regarding privacy.

- Taking a look at the Network tab on Chrome DevTools, we can see that there is a single request that loads up all the text content in the page, which suggests their using SSR (Server-Side Rendering). This is also observed in their articles pages (more on that later).

When navigating to an articles page, such as the one at
<https://code.visualstudio.com/docs/setup/setup-overview> (notice the URL structure), we can see an **Edit** button right at the top of the article:

![vs-code-article-page](https://i.imgur.com/p6m27tc.png)

and the most awesome part is that, when you click on it, you're taken to a [Git repository](https://github.com/Microsoft/vscode-docs/blob/master/docs/setup/setup-overview.md) which contains all the _text content_ for their documentation, written in Markdown! So their documentation is actually colaborative!

There's a [`vscode-docs`](https://github.com/Microsoft/vscode-docs) repo where all the Markdown content and image files are stored. In the README file they provide a guide on how to contribute to this documentation, and we can see that they have a _build_ process for their docs, which actually is closelly tied-up with their website, which unfortunaly is not open-source, so we can't go deeper into how exactly they take those mardown files and render them.

For more information on how to contribute to the content at VSCode documentation check out their [README](https://github.com/Microsoft/vscode-docs/blob/master/README.md).

## React Native (by Facebook)

React Native is an open-source JavaScript library created and maintaned by Facebook which aims to combine the best parts of native development with React, a best-in-class JavaScript library for building user interfaces. It basically allows developers to write their apps once, using React and have it run both on iOS and Android.

Their website is hosted by github.io, along with other Facebook open-source projects, at: <https://facebook.github.io/react-native/>, and their docs take you directly to their [getting started guide](https://facebook.github.io/react-native/docs/getting-started).

- The React Native documentation is fully based on articles of text with some code examples, and does not have a landing page, it's very content-centric and does not say much about _what_ is React Native.
- The source-code for the whole website is actually open-source, and we can see that they use [Docusaurus](https://docusaurus.io/en/), a documentation tool, that uses React, made to create and maintain open-source documentation (maybe worth taking a closer look at) based on Markdown.

Much like the VSCode documentation, all of the text content in article format thar compose React Native's documentation is written in Markdown so that its collaborative.

## TensorFlow (by Google)

(Taken from the TensorFlow repository [README](https://github.com/tensorflow/tensorflow/blob/master/README.md))

> TensorFlow is an end-to-end open source platform for machine learning. It has a comprehensive, flexible ecosystem of tools, libraries, and community resources that lets researchers push the state-of-the-art in ML and developers easily build and deploy ML powered applications.

The documentation on TensorFlow can be found at: tensorflow.org is divided into two main categories by the maintainers, based on their content:

- [API Reference](https://www.tensorflow.org/api_docs/)
- [Narrative Documentation](https://www.tensorflow.org/tutorials)

Each one of them is generated in two different ways:

- The API Reference documentation is generated from `docstrings` written in the TensorFlow source code, which means that the content you see in the website is being pulled from the actual source-code of TensorFlow, which is open-source and lives at: https://github.com/tensorflow/tensorflow .
- The narrative documentation is composed of tutorials and guides, similar to the content found in both React Native's and VSCode's documentations. This content is also open-source and, no surprise here, written in markdown. However, there is a unique type of content that is also part of the documentation on TensorFlow which is _a lot_ of Jupyter Notebooks. All of this content lives at: <https://github.com/tensorflow/docs>.

This documentation is by far the most _professional_ looking one, and also has other forms of content, such as video tutorials. Also, it is the only one up until this point to have support for multiple languges.

## Angular CLI (by Google)

The Angular CLI is the command-line-interface toolset for developing [Angular](https//angular.io) applications.

The documentation on this project is actually inside of the documentation for the whole Angular project by Google, which is hosted at: <https://angular.io/docs>. I'm be taking a look at the whole documentation, and not just the one for the Angular CLI.

First of all, the whole angular.io website is open-source, and it's content and source code lives at: <https://github.com/angular/angular/tree/master/aio>.

The file structure for this documentation is a bit different from the others, since it's build process is closely tied to Angular, so there are a few HTML and TypeScript files that serve as examples of implementation, but the main content of the documentation is, again, written in markdown.

It's interesting that the Angular team decided not to separate the text content from the front-end source code, different from the previous documentations we've seen so far.

## Microsoft Azure Documentation (by Microsoft)

This is very nice to see, a _documentation_ repository listed with over 7.8 thousand contributors!

The Microsoft Azure Documentation, as the name suggests, is the open-source documentation of [Microsoft Azure](https://azure.microsoft.com/), and is live at: <https://docs.microsoft.com/en-us/azure/>.

This documentation functions _a lot_ like the one for VSCode. The text content of their website lives at: <https://github.com/MicrosoftDocs/azure-docs> and is written in markdown to be collaborative.

There's not particular about the way this documentation is structured, it is indeed very similar to how the VSCode one works. The only notable differences are from more of a design stand-point, this documentation looks a bit more traditional than the VSCode one, and is **not** using React, as its part of an older website (<https://docs.microsoft.com)>).

## Angular (by Google)

Well, we've already taken a look at how Angular does things documentation-wise, so nothing new to see here.

## Kubernetes (by Google)

(This description is from the Kubernetes website)

> Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

All documentation on Kubernetes can be found at: <https://kubernetes.io/docs/home/>. And since Kubernetes is not just a piece of software, but rather has a large ecosystem built around it, there are multiple sections and categories of content.

Regardless of the variety of content in the Kubernetes documentation, much like the previous ones it also uses markdown for its text content and is open-source so that it can grow and be maintened by the community. The content lives at: <https://github.com/kubernetes/website/tree/master/content> and also has support for multiple languages.

Much like the API Reference documentation for TensorFlow, the reference documentation on the API is also generated from the source-code, using `docstring`.

## NPM

NPM is the package manager for Node.js and also a registry for JavaScript packages to live at. The main `npm` source-code is actually for its CLI, that allows developers to install and publish those packages.

Their oficial website is <https://npmjs.com>, and their documentation can be found at: <https://docs.npmjs.com/>.

Right upfront, their documentation does not seen as impresive as the ones we've talked about so far.That are a few posts to help a developer know how to get started and a few more links to articles written by their team.

The documentation found at their website is **not**  documentation, since their articles cannot be edited publically. The closest to that you can get is reporting documentation needs at their [forum](https://npm.community/c/support/docs-needed).

But, when it comes to the [CLI](https://github.com/npm/cli), which is the actual open-source project, its documentation is right there in the repository, written in markdown. So they do have open-source collaborative documentation. This is the documentation you find on your terminal when you have the `npm` CLI installed and run commands with `--help` flag attached to them. In all fairness, that's probably the most used documentation by developers by a great margin.

## DefinitelyTyped

DefinitelyTyped is a very singular type of open-source project. It is not exactly a software product, but it is the go-to repository to find high quality TypeScript type definitions for **a lot** of JavaScript packages (typically hosted at npm).

Since this repository is very different from the other ones, they do have a much simpler approach to documentation. There is a website: <http://definitelytyped.org/>, which contains a few guides to help people contributing to the project, but they say in their [README file](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/README.md) that the best source of truth is actually their README, obviously written in markdown, and that's pretty much what they have for documentation on the project itself.

It's nice to point-out their efforts to maintain README files in multiple languages to make it possible for people from different parts of the world to contribute. They currently have README files written in: English (main), Spanish, Korean, Russian and Chinese.