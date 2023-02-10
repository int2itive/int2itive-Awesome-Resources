## Center Elements Vertically and Horizontally

<span style="color: #c0c0c0;">There may be more than 8</span>
  
![image](https://user-images.githubusercontent.com/70378581/218077736-dc6e876f-580b-4a1e-b465-7bde2143609d.png)

In a front-end web interview, you may have faced the question “how to center an element vertically and horizontally?” more than once.

First look at the example HTML:

```html
<div class="parent" style="background: black; width: 200px; height: 200px">
  *<div class="child" style="background: red; width: 100px; height: 100px"></div>*
</div>
```

We get a 200px parent container and a 100px child container.

Below I will introduce 8 ways, and give a running example at the end.

**1.**
The first is the rough CSS value based on the size of the parent and child containers:

```html
<style>
  .parent {
    position: relative;
  }
.child {
    position: absolute;
    left: 50%;
    top: 50%;
    margin: -50px 0 0 -50px;
  }
</style>
```

Once the original element size changes, the CSS needs to change with it. This is not ideal. Therefore, the methods described below do not need to consider the width and height of the parent and child elements, which are more recommended.


**2.**

```html
<style>
  .parent {
    position: relative;
  }
.child {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>
```
The difference between this method and the first one is that we use transform instead of margin, which makes our CSS code no longer depend on the dimensions of the element.


3.
<style>
  .parent {
    position: relative;
  }
.child {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
  }
</style>
Remember this way, the values in all four directions must be 0.

4.
<style>
  .parent {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
  }
.child {
    display: inline-block;
  }
</style>
5.
<style>
  .parent {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
This method is probably the most widely used currently.

6.
<style>
  .parent {
    display: flex;
  }
.child {
    margin: auto;
  }
</style>
7.
<style>
  .parent {
    display: grid;
    /* The following 3 ways of writing are OK */
    /* 1 */
    /* justify-content: center;
    align-content: center; */
/* 2 */
    /* align-items: center;
    justify-items: center; */
/* 3 */
    place-content: center;
  }
</style>
8.
<style>
  .parent {
    display: grid;
  }
.child {
    align-self: center;
    justify-self: center;
  }
</style>
