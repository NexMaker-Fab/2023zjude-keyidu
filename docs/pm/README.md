
## Tools

------

**docsify:**

Use docsify to dynamically convert Markdown files to html files

Refer to tutorials and resources:

https://docsify.js.org/#/

https://www.bilibili.com/video/BV1kT4y1T7wY?p=5&vd_source=bf7032daf3b223ec5c2e15d27712e0d6

Video Tutorial 1:

![视频](./img/0.mp4 ':include :type=video controls width=80% hight=400px') 

**Typora：**

The lightweight Markdown editor uses WYSIWYG editing to provide instant previews. You can also switch to source editing mode to edit markdown documents.

Refer to tutorials and resources:

https://typora.io/



## Process

------


#### **Pre-deployment**

1.Docsify needs the Node.js environment, and doc-sify needs to run in the software, so before you start learning docsify, you need to install the Node.js environment, which is very easy to install. Click to visit [official website](https://nodejs.org/en/), and press enter.

2.After the installation is complete, open the CMD command line window (win-dows platform) and enter 'node' to run 'Node.js'. The following message indicates that the installation is successful:

```
C:\Windows\System32\node
Welcome to Node.js v19.1.0.
Type ".help" for more information.
>
```

3.Then install docsify 'and continue typing in the CMD command line window:**npm i docsify-cli -g**

4.After the installation is successful, start initializing the docsify project

```
C:\Users\myxc\Desktop>docsify init ./docs
Initialization succeeded! Please run docsify serve ./docs
```


5.Open your PC browser and visit the local port on your PC [http://localhost:3000](http://localhost:3000/)to open the home page of Create Project

#### **Go to VS Code**

Open the project folder with VS code in the following directory and edit the 'README.md' file.

![2.1](./img/3.png)

#### **document with markdown including title,header,picture,link**

title

```

# 一级标题
## 二级标题
### 三级标题

``` 

header

```

<h1>一级标题</h1>
<h2>二级标题</h2>

```

picture

``` 
![A picture](./img/2.png)

```

link

```
[A link](http://localhost:3000/)

```



#### **Sidebar deployment**

1.The sidebar setup must first create a '_sidebar.md' file and then write:

![3.3](./img/33.png)

2.Then add Settings in 'index.html' :

```
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: '😃KEYIDU',
      repo: '',
      loadSidebar: true ,
    }

```

3.Write the directory link in the _sidebar.md file:

```
<!-- docs/_sidebar.md -->

- [✔Team introduce](README.md)

- ✔Daily homework
    - [1. PM]
        - [How to build web](pm/)
    - [2. CAD]()
    - [3. Arduino]()
         - [processing](processing/)
    
- ✔Final project
    - [Description](final%20project/description.md)
    - [How to design](final%20project/how%20to%20design.md) 
    - [How to make](final%20project/how%20to%20make.md)

```


The folder hierarchy is as follows:

![3.4](./img/6.png)



#### **Coverpage**

1.To open the home page, add the following in the index:**coverpage: true**

![4.1](./img/2.1.png)

Location of coverypage.md:

![4.1](./img/2.2.png)

2.Create a '_coverpage.md' file and write:

![4.2](./img/34.png)

```
# Happy journey of learning
>
< img src="./img0/ke1.png" alt="keyidu" style="zoom:10%;" />

# 设计工程学

> All by keyidu👋

[开始学习](./README.md)

```


#### **Page beautification**

Style choice:

There are four official themes that only need to be introduced in index to be used:

![5.1](./img/8.png)

We chose the theme "blue", so we added the following code to the index to run this page beautification:

![11.1](./img/11.png)

#### **Local setting**

1.Download the github client and register

2.Try to find the repository on the client and copy it locally

3.Open the local file with vscode and edit it

4.Update the file and push it to the web page

![6.1](./img/24.png)

![6.2](./img/25.png)

![6.3](./img/26.png)

------


## **General interface layout**

![5.1](./img/23.png)

## **Collaborator setting**

![home](./img/home.png)

![invite](./img/invite.png)

![role](./img/role.png)

## **index.html document**

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
  <meta name="description" content="Description">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">
  
 
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/buble.css" />
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/sidebar.min.css" />
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/sidebar-folder.min.css" />
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: '😃KEYIDU',
      repo: '',
      loadSidebar: true ,
      subMaxLevel: 1 ,
      loadNavbar: true,   //prepare for navbar
      coverpage: true,
      onlyCover: true,
      loadNavbar: true,
      
      search: {
        noData: {
          '/': 'None!'
        },
        paths: 'auto',
        placeholder: {
          '/': 'Search...'
        }
      }
     
    }
  </script>
  <!-- Docsify v4 -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></script>

</body>
</html>

```
**Page preview**

![index1](./img/index1.png)

![index2](./img/index2.png)

## Problem and solution

------

1.Jump page level problem:

In the early stage, the sidebar page could not jump due to the editing error of the level. After understanding the relationship between the relative levels, I corrected it.

![3.1](./img/4.png)
2.Picture problem:
The image cannot be loaded because the local image file address is directly added. After referring to the structure of other people's works, re-establish the picture management folder and change the picture address.

![6.1](./img/9.png)

3.How to insert video:
The same way you inserted the photo, but with the file suffix changed to 'mp4'. And limit the size of the video.
![6.1](./img/10.png)

