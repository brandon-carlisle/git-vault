## Basic ideas

- Allow users to easily upload and share their in-game specific keybinds.
- Allow users to view their favorite content creators keybinds to use for them selves.
- Allow cc's to have keybinds for multiple games.
- Easy point and click UI for selecting keybinds for any given game
- Allow users to favorite certain keybinds profiles to return to incase of changes.

## Tech stack

- React
- NextJS
- CSS Modules
- Supabase

## Basic flow of using the app

### As user making a game config

1) Visit keybinds.app and is met with the landing page
2) Create account / login with Google account
3) Visit keybinds.app/create
4) Select game tab and will see a virtual keyboard on screen with a list of settings relevant to selected game
5) Once finished filling in settings, clicking the create config button will save the config to server/account with a shareable link. (only the creator of that config can edit/delete)
-- 

### As a user viewing their profile

1)  Visiting keybinds.app/brandon 
2)  Will have two tabs, Liked configs & My configs
3) Each tab will have a list of all the relevant configs with the ability to filter by game
4) 