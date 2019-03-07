My notes:

- When writing in React, using JSX, a flavor of Javascript

  - Check out babeljs.io
  - Looks like HTML-JS mix

- Application is made up of components

  - how to make one?

  var Mystery = React.createClass({
  // here's where we make the component itself
  render: function () {
  return(<h3>Unsolved episodes of Unsolved Mysteries</h3>);
  }
  });

- Every component can only return one parent element

  - To include multiple HTML elements, nest in a div (one parent):

  var Mystery = React.createClass({
  // here's where we make the component itself
  render: function() {
  return (
  <div>
  <h3>Simple component one</h3>
  <p>Nested elements in one component</p>
  </div>
  );
  }
  });

- ReactDOM.render can only render one component; use div trick again if you want to repeat:

        ReactDOM.render(<div>
        <Mystery />
        <Mystery />
        <Mystery />
        </div>, document.getElementById("example"));

- Passing properties to a React component. Example:

    <script type="text/babel">
      var UnsolvedMystery = React.createClass({
        render: function() {
          return (
            <div>
              <h1>{this.props.title}</h1>
              <h2>{this.props.summary}</h2>
            </div>
          );
        }
      });
  
      ReactDOM.render(
        <UnsolvedMystery
          title="Lucy Loo Hoo"
          summary="Mysterious things happening"
        />,
        document.getElementById("example")
      );

- Event handling and child property:

    var LoveNote = React.createClass({
        edit: function() {
          alert("Editing now");
        },

        remove: function() {
          alert("Removing now");
        },

        render: function() {
          return (
            <div className="commentContainer">
              <div className="commentText">{this.props.children}</div>
              <button onClick={this.edit} className="button-primary">
                Edit
              </button>
              <button onClick={this.remove} className="button-danger">
                Remove
              </button>
            </div>
          );
        }
      });

      ReactDOM.render(
        <div className="board">
          <LoveNote>Here's a pb&j because I love you</LoveNote>
          <LoveNote>I fed the dog because I love you</LoveNote>
          <LoveNote>Let's go to the discotheque because I love you</LoveNote>
        </div>,
        document.getElementById("example")
      );

- Properties vs States: states can change, properties cannot

---

![](http://i.imgur.com/5Bqs5zi.png)

React boilerplate thenewboston tutorials.

## Getting started

To get started simply download the repo using the link below. All required files are included.

https://github.com/buckyroberts/React-Boilerplate/archive/master.zip

## Setting up Gulp (optional)

You can also use Gulp to add additional build tasks. To use, follow the instructions below.

Navigate to the root directory and run the following command:

```
> npm install
```

After modules are installed, you can start watching for SCSS changes using the command:

```
> gulp
```

You can install more modules and configure them in the **gulpfile.js** file as needed.

## Links

- [Support thenewboston](https://www.patreon.com/thenewboston)
- [thenewboston.com](https://thenewboston.com/)
- [Facebook](https://www.facebook.com/TheNewBoston-464114846956315/)
- [Twitter](https://twitter.com/bucky_roberts)
- [Google+](https://plus.google.com/+BuckyRoberts)
- [reddit](https://www.reddit.com/r/thenewboston/)
