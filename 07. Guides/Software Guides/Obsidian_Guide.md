---
mindmap-plugin: basic
---
# Obsidian Guide
## About Obsidian 
Obsidian is a **note-taking and personal knowledge management app** that allows you to build a "second brain" using a system of interlinked notes. 
- Obsidian stores all your notes as **local Markdown files** (.md), giving you complete control.
- Local-first storage (no cloud dependency, unless you sync it yourself).
- Bidirectional linking and a **graph view** to visualize connections between notes.
- Support for **community plugins** for extended functionality.
- Powerful search, tags, and backlinking tools.

Obsidian's flexible pane layout allows you to split your screen into multiple sections. You can view multiple notes side by side, have your graph view open, or view backlinks and tags while editing notes.

---
## Syntax

While Obsidian fully supports **standard Markdown**, it introduces **extra features** specifically designed for knowledge management, linking, and advanced workflows.

>[!info] You can **add additional cursors** by holding `Alt` (or `Option` on macOS) and selecting another position in the note.

| **Feature**            | **Standard Markdown**            | **Obsidian Syntax**          | **Example**                     |
| ---------------------- | -------------------------------- | ---------------------------- | ------------------------------- |
| **Internal Links**     | Not supported                    | `[[Page Name]]`              | `[[My Note]]`                   |
| **Dataview Queries**   | Not available                    | Plugin-based query system    | `table from "Tasks"`            |
| **Embeds** (anything)  | Not native                       | `![[Source Name]]` for notes | `![[anyhting.ogg]]`             |
| **Tags**               | Some systems support inline tags | `#tag` within text           | `This is a #todo`               |
| **Block References**   | Not supported                    | `^block-id` for reference    | `This is a paragraph ^my-block` |
| **Tasks/Checkboxes**   | Limited support in MD            | `[ ]`, `[x]` for task lists  | `- [ ] Task`  <br>`- [x] Done`  |
| **CSS Customization**  | Limited                          | Fully customizable           | N/A                             |
| **Tables of Contents** | Manual links required            | `[[toc]]` or plugins         | N/A                             |
>[!tip] It is advised to **stick to Markdown Syntax** as it will be very portable to any other thing specially for Links. Minimize use of other complex features make it simple and minimalistic 

---

### Callouts

>[!tip]+ Callouts are Foldable !!
You can make a callout foldable by adding a plus (+) or a minus (-) directly after the type identifier.

Callouts are made in Obsidian by using type identifier with quote blocks like - 
>[!abstract] Abstract

>[!info] Info

>[!tip] Tip

>[!note] Note

>[!question] Question

>[!warning] Warning
> 

>[!danger] Danger
> 

>[!quote] Quote

>[!bug] Bug 

>[!failure] Failure 

>[!success] Success

>[!todo] Todo

---
### Properties

Metadata can be stored in **YAML(Yet Another Markup Language)**. Obsidian provides some default ones but users may also create it. Important points include :

- Type `---` at the very beginning of a file or Use the **Add file property** command.
- **Mentioned at start of a page** it has a **field or a property followed by `:` , a space and then the value**
- **Multiple values** can be added by **separating with a `,`.**

>[!tip] In addition to a name and value, properties also have a _type_. A property's type describes the kind of values it can store.

#### Supported property types:

- **Text**
- **List**
- **Number(3.1587)**
- **Checkbox(true or false)**
- **Date (2020-08-21)**
- **Date & time(2020-08-21T10:30:00)**

>[!note] Text and Lists support **Links** but **should be written in double quotes.**

>[!note] Once a property type is assigned to a property, all properties with that name are assumed to have the same property type.

#### Default properties:

| Property     | Description                                              |
| ------------ | -------------------------------------------------------- |
| `tags`       | See Tags.                                                |
| `aliases`    | See Aliases                                              |
| `cssclasses` | Allows you to style individual notes using CSS snippets. |

You can also add properties of your own and declare it at start of a page.

---
## File Organization

- Each note in Obsidian is a **Markdown (.md) file**. Markdown is a lightweight markup language that lets you format text with simple syntax. Learn Here: [Markdown Guide](Digital_Note-Making_-_Why_and_How.md)  

- **Vault:** A **vault is your workspace** in Obsidian, a folder on your computer where all your notes are stored as `.md` files. You can create multiple vaults for different purposes.

---

- **Folders :** **Primary and Easiest** Way to Organize Files. Drawback is a ~~**file can only belong to one folder**~~ at any point in time.

>[!info] **Adding Media to Notes: **Always create a folder where you can store all attachments in an organized way because unlike cloud based services things are in your storage.

- **Tags :** Tags followed by `#` can also be used for **multiple inheritance**. It links to pages as a whole. Multiple Tags are added like a list beginning with`-`.Tags can use inheritance when `/` are used

> [!info] Aliases let you assign multiple names to the same note. For example, if you have a note on "JavaScript," you can add aliases like "JS" or "ECMAScript." This makes it easier to link to the same note using different terms.

---

- **Linking :** Markdown Linking can be done but **Obsidian has an advanced and easy way** using **Bidirectional Linking** using `[[filename goes here]]` It can even **link parts of a page.** Learn it here : [Markdown Guide](Digital_Note-Making_-_Why_and_How.md)
    **Backlinks:** Automatically display notes that link to the current note.To view the backlinks for the active note, click the **Backlinks** ( ![obsidian-links-coming-in.svg > icon](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/icons/obsidian-links-coming-in.svg) ) tab in the right sidebar.
- **Graph View:** A **visual map** that shows how your notes are connected. Press `Ctrl/Cmd + G` to open the graph view.

>[!info] **File Organization:** Group related files into folders, but **avoid overly complex folder structures.** Instead **use tags and links** to organize ideas across folders.

>[!tip] A bookmark is a "shortcut" that immediately takes you the bookmarked item.
You can add bookmarks to Files, Folders, Graphs, Searches, Headings, Blocks

---
## Command Palette and Hotkeys

The Command Palette (Ctrl/Cmd + P) is a powerful feature that lets you search for any action in Obsidian. You can quickly run commands, open settings, or perform other tasks without navigating through menus.

Obsidian allows you to customize hotkeys for nearly every action. This can greatly speed up your workflow. Common Key Preferences are mentioned here : [My Key Preferences](My%20Key%20Preferences.md)

---
## Plugins 

### Templator 

 A text snippet that starts with an opening tag `<%`command tag here `%>` is what we will call a **command**. A Template contains commands.


All our functions are children of the `tp` object. To access the "child" of an object, we have to use the dot notation `.`
`tp.<my_function>(arg1_name: type, arg2_name?: type, arg3_name: type = <default_value>, arg4_name: type1|type2, ...)`

If an argument is optional, it will be appended with a question mark `?`,
If an argument has a default value, it will be specified using an equal sign `'='`
If an argument can have different types, it will be specified using a pipe `|`

Examples of Functions are listed below :

---
#### Date
##### Subclasses Include :
- **`tp.date.now`**: Inserts the current date and time.
- **`tp.date.today`**: Inserts the current date without the time.
- **`tp.date.tomorrow`**: Inserts the date of the next day.
- **`tp.date.yesterday`**: Inserts the date of the previous day.
- **`tp.date.format(format_string)`**: Customizes the format of the date (e.g., `YYYY-MM-DD`).
- **`tp.date.weekday`**: Returns the current day of the week.

##### Arguments Include :
-   `format`: Format for the date like YYYY-MM-DD
    
-   `offset`: Offset for the day, e.g. set this to `-7` to get last week's date. You can also specify the offset as a string using the ISO 8601 format like P+2M wo months from now
    
-   `reference`: The date referential, e.g. set this to the note's title
    
-   `reference_format`: The date reference format.

#### config 
##### Subclasses Include :
- **`tp.config.home`**: Returns the home directory path.
- **`tp.config.templates_folder`**: Inserts the path to the template folder.
- **`tp.config.vault_name`**: Inserts the name of the current vault.

---
#### file
##### Subclasses Include :
- **`tp.file.title`**: Inserts the title of the current file.
- **`tp.file.name`**: Inserts the name of the current file.
- **`tp.file.creation_date`**: Inserts the file's creation date.
- **`tp.file.last_modified_date`**: Inserts the last modified date.
- **`tp.file.folder`**: Inserts the folder path of the current file.
- **`tp.file.path`**: Inserts the full path to the file.
- **`tp.file.content`**: Retrieves the file's content
- **`tp.file.cursor(order?: number)`**: Sets the cursor to this location after the template has been inserted.

##### Arguments Include :
-   `filename`: The filename of the new file, defaults to "Untitled".
    
-   `folder`: The folder to put the new file in, defaults to obsidian's default location.
    
-   `open_new`: Whether to open or not the newly created file. Warning: if you use this option, since commands are executed asynchronously, the file can be opened first and then other commands are appended to that new file and not the previous file.
    

-   `template`: Either the template used for the new file content, or the file content as a string.


#### web
##### Subclasses Include - 
- **`tp.web.daily_quote()`** : Retrieves and parses the daily quote from the API 

- **`tp.web.random_picture(size?: string, query?: string)`** : Gets a random image 

##### Arguments Include :
-   `query`: Limits selection to photos matching a search term. Multiple search terms can be passed separated by a comma `,`
    
-   `size`: Image size in the format `<width>x<height>`

A specific syntax exists for whitespace control:

-   An underscore `_` at the **beginning** of a tag (`<%_`) will trim **all** whitespace **before** the command
-  An underscore `_` at the **end** of a tag (`_%>`) will trim **all** whitespace **after** the command
-   A dash `-` at the **beginning** of a tag (`<%-`) will trim **one** newline **before** the command
-   A dash `-` at the **end** of a tag (`-%>`) will trim **one** newline **after** the command.

#### User Functions
When you insert a template containing a **template variable,** Templates replaces it with its corresponding value.

|Variable|Description|
|---|---|
|`{{title}}`|Title of the active note.|
|`{{date}}`|Today's date. **Default format:** `YYYY-MM-DD`.|
|`{{time}}`|Current time. **Default format:** `HH:mm`.|

**Snippets:** CSS snippets are small pieces of custom CSS you can add to modify the look and feel of Obsidian. Create snippets to change the appearance of your notes, fonts, or overall UI.

---

### Databases
**Databases :** Initiated using **multiline code block with `dataview` as the Language** . Queries can be used for databases. Operations are performed on the **vault's metadata.**

- Supports **Table, Task, List** Only. 
- **Case-Insensitive** and **Dynamic in nature.**
- It's very user friendly yet here are some common syntax:
   -  Logical operations are simply used in words, `and`, `or`, etc.
   - `from` specifies where to pick data from, initially it's the whole vault. If location is specified with `outgoing` or `incoming` it shows all links to the file.
   - `where` works as an if condition. `contains(field,value)` shows only those things whose given field has value provided in the arguments.
   - `sort field asc` sorts things based on the field in the order specified *asc or desc*.

```dataview
List FROM "Curiosity"
```
-

---

### Other Plugins 

- **Daily Notes:** It automatically creates a new note for the current day. It's **great for journaling** or logging your activities.

- **Periodic Notes:** Extending the daily notes concept, you can also create weekly, monthly, or yearly notes to keep track of things over different time frames.

- **Advanced Tables :** For documenting syntax in programming, it is a lifesaver. It allows you to create and manipulate tables much more easily than with default Markdown

- **Obsidian Git**: For backup and version control.
- **Calendar + Periodic Notes**: For tracking learning progress and logging milestones.
- **Quick Switcher++**: To quickly navigate between notes.
- **Kanban**: For managing tasks and planning.
- **Sliding Panes**: For working with multiple notes side-by-side.
- **Note Refractor**: To break down large notes into smaller ones.
- **MarkDownload:** saves webpage entirely as md format

---