# SBScript Design Specifications

SBScript (SBS) aims to create a language with a similar syntax and feature set to modern programming languages such as C# and Swift while still compiling to highly efficient Scratch 3 (`.sb3`) projects. This is as opposed to other languages that try to emulate the structure of Scratch projects in text (see [goboscript](https://github.com/aspizu/goboscript)) while sacrificing many of the conviniences of modern languages (classes, writing code across files, etc.). As a result, SBS will lose some performance by implementing features not found natively in Scratch and the produced Scratch projects may be less readable, but this is deemed worth it in exchange for these conviniences.

## Scratch 3's Limitations

Before discussing the design of this scripting language it is important to define some of it's limitations. In case these limitations are changed their values will only be outlined in this section of the document and they will be referenced by name everywhere else.

> JSON Size Limit → 5MB:
>
> The size limit for the `project.json` file.
> Only applies to online projects, although from testing the desktop editor seems to be unstable with large files.

> Asset Size Limit → 1MB:
> 
> The size limit for each *individual* asset inside of a project.
> (The [wiki](https://en.scratch-wiki.info/wiki/Project_File_Size) lists no official limit on how many assets you can have in a project.)

> List Size Limit → 200,000 items:
>
> The maximum number of items a list can hold.

> Variable Size Limit → 10,240 characters:
>
> The maximum amount of characters a given variable **or list entry** can store.
