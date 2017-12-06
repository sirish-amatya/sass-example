# Sass Example
SASS is a pre-processor for css. Previously, css had limitations in making the css dynamic. With sass, we can now make the css dynamic by it's below mentioned features.

1. Variables
2. Nesting
3. Partials and Import
4. Mixins
5. Extend/Inheritance
6. Operators

Now we can write a sass file or a scss file and then convert into css file with simple command.

## Installation guide for Linux

Firstly, we need to install rub and rub-dev and then sass with below command

```
sudo apt-get install ruby

sudo apt-get install ruby-dev

sudo gem install sass
```

To check the installation, type the command below

```
sass -v
```

It should return Sass 3.5.3 (Bleeding Edge).

## Writing scss file

Below is an example of making use of the variables in scss

Filename: input.scss
```
$font-stack: times,Helvetica, sans-serif;
$primary-color: #333;
$bg-color: #f4ac53;

.main {
    font: 100% $font-stack;
    color: $primary-color;
    background: $bg-color;
}
```

## Executing sass

```
sass input.scss output.css
```

## Other features

### Nesting
With nesting, we can make the scss file more readable and less code to write
```
.menu {}
.menu {
    ul {
        margin: 0;
        padding: 0;
        list-style: none;
        width: 100px;
        background-color:#f1f1f1;
    }

    li {
        display: block;
        color: #000;
        padding: 2px 5px;
        text-decoration: none;
    }

    a {
        display:block;
        padding: 2px 5px;
        text-decoration:none;
    }

    a:hover {
        background-color: #555;
        color:white;
    }
}
```

### Partials and Import
Partials and import is more on separating the scss parts into different files and importing it to the scss where required. If you are using php, then it is like creating header.php and including it in other files. The filename of the partials should start with underscore.

Filename: _body.scss
```
$font-stack: times,Helvetica, sans-serif;
$primary-color: #333;
$bg-color: #f4ac53;

body {
    font: 100% $font-stack;
    color: $primary-color;
    background: $bg-color;
}

```
And import it in main css file
```
@import 'body';
```

### Mixins

You can use mixins if you want to re-use a portion of css inside the other css declaration

```
@mixin border-radius($radius, $color) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
    height: $radius;
    width: $radius;
    background: $color;
}

.circle {
    @include border-radius(50px, red);

}
```

### Inheritance

Inheritance can be used to share the property of a parent selector in child selector as below

```
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}

.warning {
  @extend .message;
  border-color: yellow;
}
```
### Operators

Operators like +, -, *, /, and % can be used in scss file as below

```
.centered {
  margin-right: auto;
  margin-left: auto;
  width: 300px/960px * 100%;
  height: 300px/960px * 100%;
  background: aqua;
  padding: 5px;
}
```
