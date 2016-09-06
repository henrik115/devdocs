---
layout: default
group: UI_Components_guide
subgroup: concepts
title: About the uiCollection class
menu_title: About the uiCollection class
menu_order: 7
version: 2.1
github_link: ui_comp_guide/concepts/ui_comp_uicollection_concept.md
---

## {{page.menu_title}}  
{:.no_toc}

* TOC
{:toc}

## What is the uiCollection 

The uiCollection class inherits from the uiElement class. This class' file path is `<UI_Module_dir>/view/base/web/js/lib/core/collection.js`. The uiCollection library class should be used as a base class by any components that contain a collection of child UI components

## Commonly used uiCollection methods

The uiCollection class implements the following methods:

* The `initElement()` method allows you to add custom functionality to the current UI component, or to a child UI component when the child UI component initializes. The `initElement()` method gets the child UI component instance as a parameter.
  Example:

  {%highlight js%}
  initElement: function (instance) {
      instance.%customProperty% = 21;
  }
  {%endhighlight%}

* The `destroy()` method is used to remove a child collection and all its dependencies.

  Example:

{%highlight js%}
    this.destroy();
{%endhighlight%}

* The `getChild()` method returns an element from child collection. 
 
  Example:
{%highlight js%}
    this.getChild(index)
{%endhighlight%}

  where `index` is child element index.


### Commonly used uiCollection properties

`elems` is the observable property that contains the child UI components collection.

As an example:

{%highlight js%}
console.log(this.elems());

// [
//   %uiComponentInstance 1 %,
//   %uiComponentInstance 2 %,
//   %uiComponentInstance 3 %,
//   %uiComponentInstance 4 %
// ]
{%endhighlight%}
