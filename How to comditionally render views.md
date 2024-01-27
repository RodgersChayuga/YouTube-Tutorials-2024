# How to comditionally render views

## Introduction:
"Hey React enthusiasts! Today, we're tackling the important topic of conditional rendering, and I'll guide you through two different approaches using examples from my codebase. We've got a classic ternary operator approach and a more elegant object mapping technique."

### Section 1: Difficult to Read and Maintain (Ternary Operator)
#### Code Example 1:
```jsx
"Let's start by examining a common but less readable approach using ternary operators.
Pay attention to how the code structure might become confusing."

import React from "react";
import { AdminView, ContributorView, GuestView } from "./components";

export const App = ({ role }) => {
  return (
    <div>
      {role === "Admin" ? (
        <AdminView />
      ) : role === "Giest" ? (
        <GuestView />
      ) : (
        <ContributorView />
      )}
    </div>
  );
};

```

#### Explanation:
```
In this example, we're using nested ternary operators to conditionally render different views
based on the user's role. While this works, it can be challenging to read and maintain,
especially as our application scales.
```

### Section 2: More Readable and Maintainable (Object Mapping)
#### Code Example 2:
```jsx
"Now, let's explore a cleaner and more maintainable approach using object mapping.
This method enhances code readability and simplifies the logic."

import React from "react";
import { AdminView, ContributorView, GuestView } from "./components";

const RolesViews = {
  GUEST: GuestView,
  ADMIN: AdminView,
  CONTRIBUTOR: ContributorView,
};

export const App = ({ role }) => {
  const CurrentView = RolesViews[role] || DefaultView;

  return (
    <div>
      <CurrentView/>
    </div>
  );
};
```

### Explanation:
``` "In this updated example, we've leveraged an object mapping technique. By associating roles with
their respective components, the code becomes more readable and maintainable.
This approach allows us to easily extend our application without the need for nested conditionals."
```
##### Let's explain more:
```
imagine you have a special box called "App" that can show different things based on who you are.
Sometimes it shows a special place for an "Admin" (someone in charge), sometimes a place for a "Guest"
(someone visiting), and sometimes a place for a "Contributor" (someone helping).

Now, instead of saying, "Show this for an Admin, show that for a Guest," we have a magical list
that knows exactly what to show for each type of person. The list is like this:

1. For a _"Guest,"_ show something called "GuestView."
2. For an _"Admin,"_ show something called "AdminView."
3. For a _"Contributor,"_ show something called "ContributorView."

Now, every time you come to your special box, you just need to say who you are, and the box knows
what to show you! If you are a "Guest," it shows the "GuestView"; if you are an "Admin," it shows
the "AdminView"; and if you are a "Contributor," it shows the "ContributorView."

But what if someone says they are something else, like a "Superhero" or a "Ninja"? To be safe,
we also have a special place called "DefaultView" that shows something when we are not sure what to show.
So, if someone says they are a "Superhero," the box will show the "DefaultView" because it doesn't
have a special place for superheroes.

That's it! It's like a magical box that knows exactly what to show for different people, and it even
has a backup plan for when it's not sure. Cool, right?
```

### Conclusion:
```
"To wrap it up, we've covered two ways to conditionally render views in React. The first, a classic
ternary operator method, which works but can become convoluted. The second, a more elegant object
mapping technique, providing improved readability and maintainability."
```

### Closing:
```
"Thanks for joining me in this tutorial! If you found it helpful, don't forget to like, share, and
subscribe for more React tips. If you have questions or other techniques you'd like to share,
drop them in the comments below. Happy coding, and I'll catch you in the next video!"
```
