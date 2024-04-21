This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.


______________________________________________________________________________________________________

To view the project, use npm run dev and follow the localhost link. Ensure dependencies are installed on your machine.

"dependencies": 
    "@hookform/resolvers": "^3.3.4"
    "next": "14.2.1"
    "react": "^18"
    "react-dom": "^18"
    "react-hook-form": "^7.51.3"
    "sass": "^1.75.0"
    "yup": "^1.4.0"

Expected path and behaviour.

Start on landing page with 2 available links. Visitors and Members

Visitors - View listings with options to go to the login page or registration page. Can also search listings

Members - Goes to login page

Register - Contains registration form and redirects to login page upon successful login with message

Login - Contains the login form, redirects to members page upon success with message

/* Dummy test data I used for testing
Name: John_Doe
Email: johndoe@stud.noroff.no 
Password: JohnD!23
Confirm Password: JohnD!23
*/

Members - Displays listings with additional option to view and place bids. Search is also available. Links to profile and create listings page

Profile - Displays some user information and grants the ability to change the avatar image url for the user. Also links back to members page and create listing page

Create - Contains the create listing form with necessary fields for updating the api. Also links to members and profile pages

______________________________________________________________________________________________________

Further points to raise regarding project:

- PROFILE_URL and CREDITS_URL have the same value, done on purpose so I could more clearly see which was being used
for credits purposes and which was being used for profile purposes

- Using Listings used to describe code are called Auctions for the user. Providing clarity for user and ease of use for devs

- Since the response from the profile endpoint doesn't return an id, I used email as a unique identifier instead

- Chose to redirect user to login page after registering an account so they can use their new credentials to access
the members page

- Search functionality works when used on both visitors and members pages, however the listings only update on the
visitors page, on members page, it searches the listings, displays a list of the matching auctions but still displays
all of the auctions regardless. I could not figure out how to implement this without breaking the Search component

- Was not able to get the functionality working for immediately updating the user's credits display in the MainHeader
component after placing a bid in the MembersItem component. The API is updated successfully, so the updated value is displayed after refreshing the page, but I would rather have it update the credits section in the header immediately

- The members page shows all listings, with 10 results per page. However I could not figure out how to get the same 
functionality working for the visitors page so needed to set the limit to 100 to pull most if not all of the results for now. This is only a temporary fix though and won't work when the amount of listings passes 100

- The search function on the visitors page produces a list of <li> elements underneath the form that match the search criteria, it also successfully filters the listings to show only the listings that match the criteria. This functionality does not work on the members page, the <li> list is generated, but all listings are still visible, so only has partial functionality

- When a user first logs in they are granted 1000 credits. This was supposed to occur once per day upon a successful login, however upon testing, no further credits were granted upon subsequent logins

- spent too long trying to achieve all functionality and did not come around to styling as I wanted to
- styling was going to be done via sass and bootstrap library

Things I wanted to do with the project that are unfinished

- wanted to convert the current date/time format to show only a date value on the listing deadlines (endsAt)
- wanted search functionality to fully work on both members and visitors pages
- wanted the functionality to pull all listings to fully work on both members and visitors pages
- wanted to style the site fully
- wanted a nicer way to notify users of success/failed actions than the window.alert method
- wanted the current bids on a listing to be hidden until a tab was opened to display them
- wanted the user's credits to immediately update upon a successful bid being placed, rather than updating after a page refresh
- wanted to test if users received credits from other users after they bid on their listings
- wanted to the user to receive 1000 credits once per day after logging in successfully

used elements and className="" for styling purposes

- h2, nav, ul, li, <Link />, footer, p, form, label, input, textarea, button, header

- index-nav, email-credits-display, disclaimer, create-listing-container, loginform-container, regform-container, search-form, update-avatar-form, footer-container, logo (width+height already set), container (layout), user-info (inside header), 
