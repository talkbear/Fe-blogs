

# 1. vertical center align

## div + div 

### display

**display:flex + align-items: center or + justify-content:center**
```
display: flex;
align-items: center;

// or
display: flex;
flex-direction: column;
justify-content: center;
```

**dispay: flex + margin: auto: apply auto margins to a flex item, the flex item will extends it's margin to occupy the extra space**

```
display: flex;
.child{
    margin: auto;
}
```
> 当你觉得align-item:center;justify-conent:center;不能满足你的需求，试试这种方式。它最大的特点就是不会限制于flex父亲元素的宽高。使其具备更大的自由性。

**display: table-cell + vertical-align:**

```
display: table-cell;
    vertical-align: middle;
    text-align: center; 
```

**dispaly:inline-block+ vertial-align, 这种方式通过使用为元素占位实现文本垂直剧中:**
```
.center::before{
    content: '';
    width: 0;
    height: 100%;
    display: inline-block;
    vertical-align: middle;
}
```

### position

**position + translate**

```
    position: relative/absolute/fixed/sticy;
    top: 50%;
    transform: translateY(-50%);
```


**postion:absolute/fixed/sitcy + 0:**

```
  width: 50%; 
  height: 50%; 
  background: #000;
  overflow: auto; 
  margin: auto; 
  position: absolute; 
  top: 0; left: 0; bottom: 0; right: 0; 
```

### line-height

这种方式多用于指定有宽高时：
```
.parent{
    line-height: 200px;
}
.child{
    // if height auto do nothing , the child will inherite the parent line-height
    
    // if height set implictly, let the height equals to parent line-height

    height: 200px;
}
```

```
.child{
    line-height: 200px;
    height: 200px; // for the line-height is inherit from the parent , so it's like the previous one 
}
```

## div + span

```
line-height: 200px;
display: inline-block;
height: 200px;
```

# 2. horizontal center align 

## div + div

### position

**定宽高时**
```
position: relative/absolute/fixed/sticky;
left: 50%;
transform: tranlate(-50%);
```

**定高不定宽时**

```
position: absolute/fixed;
left: 0;
right:0;
```

### display

**定宽高时**

居中元素添加
```
display: block/flow-root/list-item;
display: inline-block;
text-align: center;
```
```
display: block/flex/flex-root/grid/table/inline-block/inline-xxx；
margin-left: 50%;
transform: translate(-50%);
```

给父元素添加
```
display: flex;
justify-content: center;

```

### margin

```
display: flex/block/table/list-item;
margin: 0 auto;
```

```
margin: 50%;
transform: translate(-50%);
```

## div + span

文本居中：


```
text-align: center;
```

```
display:flex;
justify-content: center;
```

```
display:block;
margin: 0 auto;
```

```
display:block;
text-align:center;
.center{
    display:inline-block;
}
```

## span + span

```
text-align: center;
```

# 3. vertical and horizontal center align


## div + div 

### position:relative

1.absolute + translate

```
position: relative;
left: 50%;
top: 50%;
transform: translate(-50%);
```
> 优势：不会影响其他元素。

### position:absolute 

1. absolute + translate

```
position: absolute;
left: 50%;
top: 50%;
transform: translate(-50%);
```

2. absolute + scale

```
position: absolute;
left:0;
right0;
top:0;
bottom:0;
transform: scale(.x); 
```

### margin

```
margin: auto;
```

