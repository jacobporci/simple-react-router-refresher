## Why React Router?

React Router, and dynamic, client-side routing, allows us to build a single-page web application with navigation without the page refreshing as the user navigates. React Router uses component structure to call components, which display the appropriate information.

By preventing a page refresh, and using Router or Link, which is explained in more depth below, the flash of a white screen or blank page is prevented. React router also allows the user to utilize browser functionality like the back button and the refresh page while maintaining the correct view of the application.

## Using React Router

First, install React Router, using either yarn or npm.

    yarn add react-router-dom

Note that in the documentation and in the API, the actual component is called Browser Router . Some people prefer to simply refer to the component as Router, so you may see it aliased or choose to alias it in code, in which case it will be referred to as <Router> as long as it as been imported with an alias.

    import { BrowserRouter } from ‘react-router-dom’

    //alternatively, aliased

    import { BrowserRouter as Router} from ‘react-router-dom’

When not using React Router, **App** is often the highest parent component in React apps. With React Router, however, the **Router component needs to be the highest parent**. This just lets all of the component use the power of Router, because as a parent, it passes down all of its props to its children, and thus the entire application.

To set this up most simply, in index.js, include:

    ReactDom.render(<Router><App /></Router>)

## React Router <Link>

Using `<Link>` functions similarly to using an `<a>` tag, but, as mentioned above, prevents a page refresh, and looks like a React component (because it is!).

For example, if you want a link to contact information,

    <Link to= “/contact”>Contact Us</Link>

Using **Link** will navigate the user to **/contact**, and the URL will change, **without the page reloading**!

Where does this get included in the application? The **Router** component functions like a control center, and **connects the route path (link) with the React component that should appear on the page**.

    <Route path="/contact" component={ContactPage} />

At its most basic, this is client-side routing.

**Additional Note:**
Setting the path to just “**/**” — it effectively wraps, or shows up on every page. This is particularly helpful for things like a
**navigation bar, a footer, a sign in/out toggle button** . So, at any point that the path has “/” in it — it is a match and the component will render.
