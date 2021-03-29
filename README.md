#  AI Explorer

A graphical neural net editor.

## Overview

AI Explorer is a Mac application that allows the user to graphically design neural networks. It should support most layer types used by TensorFlow and ML Compute, but it is also designed to work with other neural network libraries.

## Dependant Libraries

The application uses numerous libraries in its implementation.

  - **AJRFoundation:** Core library extending the functionality of base Unix libraries and Apple's Foundation framework.
  - **AJRInterfaceFoundation:** Core library extending the functionality of CoreGraphics, AppKit, and UIKit.
  - **AJRInterface:** Core library extending the functionality of AppKit.
  - **Draw:** Library for coordinating the drawing of vector graphics. This provide basic graphic primitives such as ovals, rectangles, and text. It also provides an architecture for adding additional graphic objects.
  - **AIExplorer:** Extends Draw to add objects for creating neural network layers. The framework actually contains the bulk of the code of AI Explorer, with AI explorer just being a wrapper to provide the sugar necessary to be a Mac application.

## Checking Out the Code

To build AI Explorer, you'll need to checkout the above frameworks along with an Xcode workspace. To checkout the code, you'll first want to create some directories. These aren't strictly necessary, but the provided workspace will require these directories.

First, create a directory where you'd like to hold your code. This directoy isn't specific, so use whatever you'd like. From now on, we'll refer to this directory as `<my_source>`.

Next, create two directories, Frameworks and Applications. You should now have the directories:

    1. <my_source>/Frameworks
    2. <my_source>/Applications
    
So, from a Unix command line point of view, you've done:

```
mkdir <my_source>
cd <my_source>
mkdir Frameworks
mkdir Applications
```
    
If you haven't already guessed, you'll now change into `<my_source>/Frameworks` directory and chceck out the framework projects. All the projects are located on GitHub. The repositories are current private, so you'll need to request access by e-mail AJ Raftis <araftis@calpoly.edu>.

To checkout the projects, do:

```
cd <my_source>/Frameworks
git clone https://github.com/araftis/AJRFoundation.git
git clone https://github.com/araftis/AJRInterfaceFoundation.git
git clone https://github.com/araftis/AJRInterface.git
git clone https://github.com/araftis/Draw.git
git clone https://github.com/araftis/AIExplorer.git
cd <my_source>/Applications
git clone https://github.com/araftis/Papel.git (optional)
git clone https://github.com/araftis/AI-Explorer.git "AI Explorer"
cd <my_source>
git clone https://github.com/araftis/Public-Workspaces.git "Public Workspaces"
```

You should now have all the code, with a few notes. One, when checking out AI-Explorer, make sure to include the "AI Explorer" parameter. This is because the application contains a space in the application name. This isn't 100% necessary, but the workspace will expect it, so without the space, you'd need to create your own workspace.

You can now navigate with Finder into "Public Workspaces". There you'll see the file "AI Explorer.workspace". Go ahead and open that workspace by double clicking on the file. If you're a Unix-head, you could also do:

```
open Public\ Workspaces/AI\ Explorer.xcworkspace
```

from the command line. You're now ready to the bulid the project. Note that you may have a couple of broken projects in your workspace. This is OK, as we won't be using these. They're present for the convenience of searching projects, especially since Xcode can only have a project open in one workspace at a time.

### GitHub Project

We've started a project at GitHub to track this [project](https://github.com/users/araftis/projects/1). This is where we'll track issues, to-dos, etc... If you'd like to be involved in the project, please make sure you're going here.

## Building

Once you've opened the workspace in Xcode, you should be ready to build. However, you need to build the right thing. By default, Xcode will scan all the projects contained by the workspace and produce a list of targets that can be built. Generally, we'll be working with the "AI Explorer" scheme, so make sure this is the selected scheme. We choose this scheme, because Xcode understands the project dependencies, so when we select this scheme, Xcode understands that AI Explorer depends on AIExplorer.framework, which depends on Draw.framework, which depends on AJRInterface.framework, etc... Thus, when you build AI Explorer, Xcode will build all dependent projects.

As you've now selected the "AI Explorer" scheme, by choosing it in the popup button located at the top of your workspace window (you should see something like: AI Explorer > My Mac). If this is true, you can build your project by choosing "Product -> Build", or as a convenience, just type cmnd-b. Once built, you can run by choosing "Product -> Run", or just cmnd-r. Note that this will also build the project, so as a short cut during development, you can just generally do cmnd-r.

## License

I'm releasing this under a BSD license.

```
Copyright (c) 2021, AJ Raftis and AI Explorer authors
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:
* Redistributions of source code must retain the above copyright notice, this 
  list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, 
  this list of conditions and the following disclaimer in the documentation 
  and/or other materials provided with the distribution.
* Neither the name of the AI Explorer nor the names of its contributors may be 
  used to endorse or promote products derived from this software without 
  specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND 
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED 
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE 
DISCLAIMED. IN NO EVENT SHALL AJ Raftis BE LIABLE FOR ANY DIRECT, INDIRECT, 
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT 
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR 
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF 
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE 
OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF 
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
