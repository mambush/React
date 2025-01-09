# React

# Creating and nesting components 
React apps are made out of components. A component is a piece of the UI (user interface) that has its own logic and appearance. A component can be as small as a button, or as large as an entire page.

# React components are JavaScript functions that return markup:

function MyButton() {
  return (
    <button>I'm a button</button>
  );
}

# Now that you’ve declared MyButton, you can nest it into another component:

export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}

# Notice that <MyButton /> starts with a capital letter. That’s how you know it’s a React component. React component names must always start with a capital letter, while HTML tags must be lowercase.

Have a look at the result:

function MyButton() {
  return (
    <button>
      I'm a button
    </button>
  );
}

export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}

The export default keywords specify the main component in the file.

The export declaration is used to export values from a JavaScript module. Exported values can then be imported into other programs with the import declaration or dynamic import. The value of an imported binding is subject to change in the module that exports it — when a module updates the value of a binding that it exports, the update will be visible in its imported value.

In order to use the export declaration in a source file, the file must be interpreted by the runtime as a module. In HTML, this is done by adding type="module" to the <script> tag, or by being imported by another module. Modules are automatically interpreted in strict mode.

Javascript Syntax:

// Exporting declarations
export let name1, name2/*, … */; // also var
export const name1 = 1, name2 = 2/*, … */; // also var, let
export function functionName() { /* … */ }
export class ClassName { /* … */ }
export function* generatorFunctionName() { /* … */ }
export const { name1, name2: bar } = o;
export const [ name1, name2 ] = array;

// Export list
export { name1, /* …, */ nameN };
export { variable1 as name1, variable2 as name2, /* …, */ nameN };
export { variable1 as "string name" };
export { name1 as default /*, … */ };

// Default exports
export default expression;
export default function functionName() { /* … */ }
export default class ClassName { /* … */ }
export default function* generatorFunctionName() { /* … */ }
export default function () { /* … */ }
export default class { /* … */ }
export default function* () { /* … */ }

// Aggregating modules
export * from "module-name";
export * as name1 from "module-name";
export { name1, /* …, */ nameN } from "module-name";
export { import1 as name1, import2 as name2, /* …, */ nameN } from "module-name";
export { default, /* …, */ } from "module-name";
export { default as name1 } from "module-name";

nameN
Identifier to be exported (so that it can be imported via import in another script). If you use an alias with as, the actual exported name can be specified as a string literal, which may not be a valid identifier.

# Description
Every module can have two different types of export, named export and default export. You can have multiple named exports per module but only one default export. Each type corresponds to one of the above syntax.

# Writing markup with JSX 
The markup syntax you’ve seen above is called JSX. It is optional, but most React projects use JSX for its convenience. All of the tools we recommend for local development support JSX out of the box.

JSX is stricter than HTML. You have to close tags like <br />. Your component also can’t return multiple JSX tags. You have to wrap them into a shared parent, like a <div>...</div> or an empty <>...</> wrapper:

function AboutPage() {
  return (
    <>
      <h1>About</h1>
      <p>Hello there.<br />How do you do?</p>
    </>
  );
}
If you have a lot of HTML to port to JSX, you can use an online converter.

# Adding styles 
In React, you specify a CSS class with className. It works the same way as the HTML class attribute:

<img className="avatar" />

#  Then you write the CSS rules for it in a separate CSS file:

/* In your CSS */
.avatar {
  border-radius: 50%;
}
React does not prescribe how you add CSS files. In the simplest case, you’ll add a <link> tag to your HTML. If you use a build tool or a framework, consult its documentation to learn how to add a CSS file to your project.

# Displaying data 
JSX lets you put markup into JavaScript. Curly braces let you “escape back” into JavaScript so that you can embed some variable from your code and display it to the user. For example, this will display user.name:

return (
  <h1>
    {user.name}
  </h1>
)

