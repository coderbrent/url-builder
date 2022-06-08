# Campaign URL Builder

This URL builder tool is designed in the same vein as this https://ga-dev-tools.web.app/campaign-url-builder/ but with some more "enterprise" grade features:

1. Ability to create multiple url "campaigns" with additional custom parameters to cover more extensive analytics based campaigns in bulk.

2. Ability to export created campaigns to a CSV file.

I built this initially for the marketing team at my place of employment, but I decided recently to white label it to show off on my personal portfolio. My portfolio hasn't been getting much love lately so I felt like providing it with a little boost!

On the engineering side of things, I developed this tool with: 

- Create React App
- Material UI 
- Netlify Serverless functions (aka Lambdas if you're more familiar with the AWS variant)

If you dig around the codebase, you'll notice I adopted a "redux-like" pattern by taking advantage of the useReducer hook to manage the application state, while avoiding diving into full blown redux. I did this because initialy this tool was only meant to add very minor additional functionality to the OG Google Analytics URL builder and I wanted to keep the complexity at a minimum. However, as things have a tendency to do, more features were requested and so the project needed to scale. I will likely revisit this implementation somewhere down the line and just convert the project into a full on RTK/Redux build, but for now I'm going to try to stretch the limits of what the useReducer hook is capable of. I'll likely add immer in, as I think it will make for easier/better handling of the reducer state (Spent some time reading the RTK docs and realizing I need to clean up those reducer functions quite a bit!)

## Engineering Project Timeline:

1. Converting to Typescript
2. Jest/RTL tests
3. Bring immer in to better handle the reducer logic

## Feature/Client facing Timeline:

1. Add user login and a proper backend to allow the creation of saved URLs with a tighter Bit.ly integration (show in the dashboard Bit.ly stats like how many URL shortenings are left on the linked account etc.)