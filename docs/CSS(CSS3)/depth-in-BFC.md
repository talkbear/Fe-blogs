# BFC(Block Formating Context)

You might have never heard a concept of BFC before, but you do known about The Box Model. the latter lie in the former. It's the 
region in which the layout of block boxes occurs and in which floats interact with other elemnts.  Thinking of BFC as the bigger box model that contains normal box model.

The first and biggest BFC is the html element,  in which all sub BFCs are included.

## how to create a BFC 

A browser creates BFCs when needed. also, BFC can triggerd through explictly set.

A block formatting context is created by at least one of the following:

Element|Prerequisite
-|-
HTML|无条件；默认第一个BFC
*| float != none
*| position: absolute, fixed
*| display: inline-block
*| display: flow-root
Block Elements | overflow != visible
*| direct children of element with display: flex or inline-flex
*| direct children of the element with display: grid or inline-grid
*|display: table-cell
*|display: table-caption
*|display: table, table-row, table-row-group, table-header-group, table-footer-group, inline-talbe
*|others...


## features of BFC

### A block formatting context contains everything inside of the element creating it.

we use the overflow: auto to clear float base on this feature.

```
<div class="outer">
      <div class="float">I am a floated element.</div>
      I am text inside the outer box.
    </div>
<style>
.outer {
  overflow: auto;
}
.float{
  float:left;
}
</style>
```


### The BFC prevents margins collapsing

The BFC contains everything include the element's margin. this enable us to handle the margin collapsing.

```
.outer {
       background-color: #ccc;
      margin: 0 0 40px 0;
      overflow: auto; // this is the key to avoid margin collapsing
    }

    p {
      padding: 0;
      margin: 20px 0 20px 0;
      background-color: rgb(233,78,119);
      color: #fff;
    }
```


### A BFC stops content wrapping floats

A BFC disalbe defaut beavior of content wrapping floats


```
<div class="outer">
      <div class="float">I am a floated element.</div>
      <div class="text">I am text</div>
    </div>
    <style>
      .outer{
        overflow: auto;
      }
      .float{
        float: left;
      }
    </style>
```


