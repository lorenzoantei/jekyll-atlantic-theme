---
title: "Replace with symbol"
date: 2021-12-30 15:40:00 +0100

categories: ["Adobe Illustrator"]
description: "Replace filled shapes with simbols"
thumbnail: "https://i.stack.imgur.com/nbCNE.png"
image: "https://i.stack.imgur.com/nbCNE.png"

layout: post
---

<div class="flex justify-center">
<a class="p-6 border bg-red-700 hover:opacity-70 transition duration-300 ease-in-out text-bold hover:text-white" href="../../collections/precious/ai/ai__replace-with-symbol.js" download>Click to Download</a>
</div>

```
/*
JET_ReplaceWithSymbol.jsx
A Javascript for Adobe Illustrator
Purpose: Replaces selected items with Instances of a Symbol from the Symbols Panel.
The desired Symbol can be defined by its index number (its number of occurrance in the Panel).
*/
var docRef=app.activeDocument;
var symbolNum=prompt("Enter the number of the Symbol you want to replace each selected object",1);
for(i=0;i<docRef.selection.length;i++){
          var currObj=docRef.selection[i];
          var currLeft=currObj.left;
          var currTop=currObj.top;
          var currWidth=currObj.width;
          var currHeight=currObj.height;
          var currInstance=docRef.symbolItems.add(docRef.symbols[symbolNum-1]);
          currInstance.width*=currHeight/currInstance.height;
          currInstance.height=currHeight;
          currInstance.left=currLeft;
          currInstance.top=currTop;
          currInstance.selected=true;
          currObj.remove();
          redraw();
}
```

[fonte](http://bcrockett.com/blog/2016/12/change-or-replace-multiple-objects-in-illustrator-using-symbols/)
