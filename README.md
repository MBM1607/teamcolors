# Team Colors

![TeamColors screenshot](http://i.imgur.com/XbWE9cG.png)

[Team Colors](http://jim-nielsen.com/teamcolors) is a reference of HEX, RGB, CMYK, and Pantone color values of major league sports teams.

## How-To

Install: `yarn install`
Development: `yarn start`
Build: `yarn build`

## How It Works

Site is built on the react framework. `index.html` is the shell container for react app. If javascript is not supported, a link is shown to the raw JSON data which has all color information.

Color data is housed in a single `.json` file `src/teams.json`. Any changes to team colors can be done there. _Note on colors_: Color definitions for each team are in arrays and grouped by color mode. Color values should match index position in the array across color modes, for example:

```
colors:
  rgb: TEAMS-RGB-BLUE, TEAMS-RGB-RED
  hex: TEAMS-HEX-BLUE, TEAMS-HEX-RED
```

Source artwork for each team is grouped by league in `sketch`. Production versions of these logo should be in `.svg` format in `public/img`.

### Edit Team Color or Name

Find teams `.json` file in `src/teams.json`, and edit the info you need.

### Add a Team

1. Determine the team’s league
2. Following the established pattern, add the team’s name and colors the `.json` file
3. Add a vector logo for the team in its corresponding `.sketch` league file in `sketch` with the team’s name (as referenced in its `.json` file) in lowercase with hyphens, i.e. "utah-jazz"
4. Export the team’s `.svg` logo to `public/img/`
5. Preferably, optimize the svg (with a tool like [SVGO](https://github.com/svg/svgo))
6. Run `yarn build`, commit, push

## Official Color References

### NBA

All NBA colors are official ([source](http://courtside.nba.com/QuickPlace/nbalogo/Main.nsf/$defaultview/AD4C002C7D0F37A285257D660058EAED/$File/NBA%20Primary%20Composite_14-15PLAYOFFS.pdf?OpenElement) user & pass: nbamedia).

The NBA only provides RGB, CMYK, and Pantone colors for each team, so the HEX color is a programmatic conversion of the RGB color.

### NFL

All NFL colors are official (see sources below).

The NFL provides official RGB, HEX, CMYK, and Pantone colors (so none of the colors you see on Team Colors are conversions).

The NFL has logo slicks which detail team color values. These are provided on a per-conference basis. _Note_: each of these source links are over 100MB in size, so they take a while to download.

- [AFC North](http://www.nflmedia.com/afc_north.zip)
- [AFC South](http://www.nflmedia.com/afc_south.zip)
- [AFC East](http://www.nflmedia.com/afc_east.zip)
- [AFC West](http://www.nflmedia.com/afc_west.zip)
- [NFC North](http://www.nflmedia.com/nfc_north.zip)
- [NFC South](http://www.nflmedia.com/nfc_south.zip)
- [NFC East](http://www.nflmedia.com/nfc_east.zip)
- [NFC West](http://www.nflmedia.com/nfc_west.zip)

### MLB

MLB colors have been extracted from the official “RGB Digital Art” spot color logo slicks provided at [MLB Press Box](http://mlbpressbox.mlbstyleguide.com) (user account required). They were not explicitly stated values, but they are color values pulled from individual team logos in an _official_ MLB document.

The extracted colors are in HEX form and their RGB counterparts are generated programmatically.

- [American League logo slick](http://i.imgur.com/RP5kBSI.png)
- [National League logo slick](http://i.imgur.com/FcuizSx.png)

### NHL

NHL colors are official. As per [Michael Sharer](https://github.com/epitaphmike) of the NHL.

### MLS

MLS colors are currently approximations, with the exceptions listed below. I am working on getting official colors of the remaining teams.

- [Philadelphia Union](http://portfolios.scad.edu/gallery/36587433/Philadelphia-Union-Brand-Guidelines)

### EPL

These leagues’ teams and colors are currently approximations. I am working on getting official colors. If you know how/where to find them, please open an issue here in Github.

## To-Dos

- [ ] Switch to `flex` for layout
- [ ] Improve filtering with fuzzy string search
- [ ] Improve error states for when data doesn't render
- [ ] Consider alternatives to no-js users rather than just "here's the raw data" (something that doesn't required a build if a single color in the JSON file is changed)
- [ ] Possibly add team `id` manually to JSON file ??

---

TODO