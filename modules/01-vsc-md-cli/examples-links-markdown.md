# Examples of Paths and URLs

Here I provide tips and examples for using Markdown to link resources located in your local machine or from a www location. In this case, we will create hyperlinks to local and web resources and will also show linked images within the Markdown document.

Please note that VS Code provides path completion assistance (via Intellisense) that will help with the creation of links to files and images. Path assistance is shown automatically by IntelliSense as you type the path of an image or link or, when not automatically shown, can be manually requested by using Ctrl+Space.

## Paths relative to the current file

Paths starting with ./ or without any prefix are resolved relative to the current file. This means that the target location will be relative to the directory in which the Markdown file is located. If the md file is located in C:\users\jane\markdown\, and your target image is in the same directory, you need to only write the file name.

```markdown
![Image in same directory](1658592183910.png)
```

Let's say that the target file is not in the current file directory but is in a folder called 'assets' located one level up (i.e. C:\users\jane\markdown\assets\) you would write:

```markdown
![Image in same directory](assets/1658592183910.png)
```

## Paths from root directory

If the resource is located in the root directory, or if you find it easier to specify the location from the root, you can begin the location with a `\`.

I.E.

```markdown
![image from root directory](/assets/md-image.png)
```

## Paths from resources below your root

Files located below your root directory will not be able to be resolved within VSC, nor would they be resolved if they were synced to a git repo.

## Paths for web urls

If the image is on the web, you write:

```markdown
![image from web](https://media.licdn.com/dms/image/D4D12AQF6rbViry8xvA/article-cover_image-shrink_600_2000/0/1658592183910?e=2147483647&v=beta&t=33LzSM3AcA7ROa6ng1ZYvo_j_hbT1k37rp2mZoEz9Jw)
```
