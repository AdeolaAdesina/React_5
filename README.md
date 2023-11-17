# React Component Interacting

A React application can contain dozens, or even hundreds, of components.

Each component might be small and relatively unremarkable on its own. When combined, however, they can form enormous, fantastically complex ecosystems of information.

In other words, React apps are made out of components, but what makes React special isn’t the components themselves. What makes React special is the ways in which components interact.

This lesson is an introduction to components interacting. After this lesson, you should be familiar with:

- how components can reference other components.
- how this allows us to separate our components into separate files.



## Returning Another Component

As we’ve seen before, each React component is responsible for one piece of the interface. As the application grows in complexity, components need to be able to interact with each other to support the features needed.

So far, we’ve explored components that return JSX elements, such as:

```
function PurchaseButton() {
  return <button onClick={()=>{alert("Purchase Complete")}}>Purchase</button>
}
```

In this example, the React component is not interacting with other components. However, you can have components interact with each other by passing information or even returning other components.

```
function PurchaseButton() {
  return <button onClick={()=>{alert("Purchase Complete")}}>Purchase</button>
}

function ItemBox() {
  return (
    <div>
      <h1>50% Sale</h1>
      <h2>Item: Small Shirt</h2>
      <PurchaseButton />
    </div>
  );
}
```

In the above example, ItemBox returns an instance of PurchaseButton. This is an example of how a component can reference other components!


E.g

```
import React from 'react';

function Picture() {
  return <img src="https://content.codecademy.com/courses/React/react_photo-octopus.jpg" />;
}

function Profile() {
  return (
    <>
      <Picture />
      <h1>Name: Octavia</h1>
      <h2>Species: Octopus</h2>
       <h2>Class: Cephalopoda</h2>
    </>
  )
}

export default Profile;
```

![Screenshot 2023-11-17 at 05 50 24](https://github.com/AdeolaAdesina/React_5/assets/29931071/97a1118b-36cc-4743-bfcf-5615839f08c8)


E.g 

The code editor has two files: ProfilePage.js and NavBar.js.

Complete the <ProfilePage /> component by having it return a <NavBar /> component above <h1>All About Me!</h1>.

Don’t forget to import the necessary component!



NavBar.js:

```
import React from 'react';

function NavBar() {
    const pages = ['home', 'blog', 'pics', 'bio', 'art', 'shop', 'about', 'contact'];
    const navLinks = pages.map(page => {
      return (
        <a href={'/' + page}>
           &nbsp;{page}
        </a>
      )
    });

    return <nav>{navLinks}</nav>;
}
export default NavBar;
```


![Screenshot 2023-11-17 at 05 53 59](https://github.com/AdeolaAdesina/React_5/assets/29931071/19ba2df1-0674-4df9-8560-20c3e5269312)


ProfilePage.js:

```
import React from 'react';
import NavBar from './NavBar'

function ProfilePage() {
  return (
    <div>
        
      <NavBar />  
      <h1>All About Me!</h1>
      <p>I like movies and blah blah blah blah blah</p>
      <img src="https://content.codecademy.com/courses/React/react_photo-monkeyselfie.jpg" />
    </div>
  );
}

export default ProfilePage;
```


![Screenshot 2023-11-17 at 05 54 43](https://github.com/AdeolaAdesina/React_5/assets/29931071/2a46b722-190c-4b6d-bbde-dbd3bd4994ab)









