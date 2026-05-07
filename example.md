---
layout: theme
title: Claude-Like Theme Example
category: theme
homepage: https://github.com/fx-slayer/typora-cc-theme
built-in: false
author: fx-slayer
typora-root-url: ./
---

# Claude-Like Theme Example

这是一个用于检查 Typora 主题效果的示例文档，覆盖正文、表格、代码块和主要 Mermaid 图表元素。

## 基础 Markdown

你可以用它写技术笔记、课程总结、论文阅读记录，也可以整理 AI 对话内容。整体风格偏安静、简洁，适合持续阅读。

### 表格

| 功能     | 说明                 |
| -------- | -------------------- |
| 标题层级 | 更清晰               |
| 表格样式 | 更统一               |
| 代码高亮 | 更易读               |
| Mermaid  | 适配预览和导出样式   |

### 行内代码

比如 `print()`、`Hello, World!`、`claude-like.css` 这类内容会有单独样式。

### 代码块

```python
def hello(name: str) -> str:
    return f"Hello, {name}!"

print(hello("Typora"))
```

## Mermaid 示例

### Flowchart

```mermaid
flowchart TD
    start([Start]) --> input[/Read Markdown/]
    input --> check{Has Mermaid?}
    check -- Yes --> render[Render Diagram]
    check -- No --> article[Render Article]
    render --> export[(Export PDF)]
    article --> export

    subgraph Theme
        cssVars[Apply CSS Variables]
        typography[Apply Typography]
    end

    render --> cssVars
    cssVars --> typography
    typography --> export
```

### Sequence Diagram

```mermaid
sequenceDiagram
    actor User
    participant Typora
    participant Theme as Claude-Like Theme
    participant Exporter

    User->>Typora: Open example.md
    Typora->>Theme: Load claude-like.css
    Theme-->>Typora: Apply document styles

    alt Diagram exists
        Typora->>Theme: Style Mermaid SVG
        Note over Typora,Theme: Actors, lines, labels and notes use theme colors
    else Plain Markdown
        Typora->>Theme: Style headings, tables and code
    end

    loop Preview or export
        Typora->>Exporter: Render document
        Exporter-->>User: PDF / HTML output
    end
```

### Class Diagram

```mermaid
classDiagram
    class Theme {
        +String name
        +String stylesheet
        +applyTypography()
        +applyMermaidStyles()
    }

    class MermaidDiagram {
        +String type
        +render()
    }

    class TyporaDocument {
        +String title
        +exportPDF()
    }

    TyporaDocument "1" --> "1" Theme : uses
    TyporaDocument "1" --> "*" MermaidDiagram : contains
    Theme ..> MermaidDiagram : styles
```

### State Diagram

```mermaid
stateDiagram-v2
    [*] --> Editing
    Editing --> Previewing: open preview
    Previewing --> Exporting: export document
    Exporting --> Done
    Done --> [*]

    Editing --> Editing: update Markdown
    Previewing --> Editing: revise content
```

### Entity Relationship Diagram

```mermaid
erDiagram
    DOCUMENT ||--o{ DIAGRAM : contains
    DOCUMENT {
        string title
        string path
    }
    DIAGRAM {
        string type
        string source
    }
    THEME ||--o{ DOCUMENT : styles
    THEME {
        string name
        string css_file
    }
```

### Gantt Chart

```mermaid
gantt
    title Theme Cleanup Plan
    dateFormat  YYYY-MM-DD
    section Cleanup
    Remove variants       :done,    a1, 2026-05-07, 1d
    Simplify README       :done,    a2, 2026-05-07, 1d
    Add examples          :active,  a3, 2026-05-07, 1d
    section Release
    Package main CSS      :         b1, 2026-05-08, 1d
```

### Pie Chart

```mermaid
pie showData
    title Example Content Mix
    "Markdown" : 35
    "Code" : 20
    "Mermaid" : 40
    "Notes" : 5
```

### User Journey

```mermaid
journey
    title Writing with the Theme
    section Draft
      Write notes: 5: User
      Add diagrams: 4: User
    section Review
      Preview in Typora: 5: User
      Export PDF: 4: User
```

### Timeline

```mermaid
timeline
    title Theme Repository
    2026-05-07 : Keep main theme only
               : Document Mermaid styling
               : Add comprehensive examples
```
