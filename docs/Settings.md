# Settings

Calendaria settings are accessed via **Settings > Module Settings > Calendaria > Calendaria Settings**.

The settings panel is organized into tabs. GM-only tabs are marked below.

---

## Calendar (GM Only)

### Active Calendar

Select which calendar system to use. Changing this requires a world reload.

- Default: `gregorian`

### Open Calendar Editor

Button to launch the Calendar Editor for creating/modifying calendars.

### Import Calendar

Button to open the calendar importer for Simple Calendar, Fantasy Calendar, and other formats.

---

## Notes (GM Only)

### Custom Categories

Create custom note categories with:

- **Name**: Category display name
- **Color**: Category color (hex)
- **Icon**: FontAwesome icon class (e.g., `fas fa-bookmark`)

---

## Time (GM Only)

### Sync Scene Darkness

Automatically adjust scene darkness based on time of day.

- Default: `true`

### Advance Time on Rest

Advance world time when players take short/long rests.

- Default: `false`

### Advance Time on Combat

Advance world time when combat rounds change.

- Default: `false`

### Real-Time Clock Speed

Configure how fast the in-game clock advances in real-time mode.

- **Multiplier**: How many units pass per real second (1-60)
- **Unit**: What time unit advances (seconds, minutes, hours)
- Example: "10 minutes per second" means 1 real second = 10 in-game minutes
- Default: `1 minute per second`

### Sync with Game Pause

Clock automatically stops when the game is paused and resumes at 1:1 real-time when unpaused.

- Default: `true`

### Sync with Combat

Clock automatically stops during active combat. Time advances per-turn via system integration.

- Default: `true`

**Note:** When sync is enabled and blocked (paused or in combat), manually starting the clock shows a warning notification.

---

## Moons (GM Only)

### Show Moon Phases

Display moon phase information in the calendar UI.

- Default: `true`

---

## Weather (GM Only)

### Temperature Unit

Choose temperature display format.

- Options: `Celsius`, `Fahrenheit`
- Default: `celsius`

### Climate Zone

Select the active climate zone (if defined in the calendar).

### Custom Weather Presets

Create custom weather conditions with an inline editor UI:

- **Name**: Condition display name
- **Icon**: FontAwesome icon class
- **Color**: Condition color (hex)
- **Temperature Range**: Min/max temperature for this condition

Custom presets appear in the Calendar Editor Weather tab and Climate dialogs alongside built-in conditions.

---

## Appearance

### Theme Colors

Customize UI colors for various components. Options include:

- Apply preset themes
- Edit individual color values
- Reset to defaults
- Export/import theme configurations

---

## Formats (GM Only)

Configure date/time display formats for different UI locations. Each location supports separate GM and player formats.

### Locations

- **HUD Date**: Date display on Calendaria HUD
- **HUD Time**: Time display on Calendaria HUD
- **MiniCalendar Header**: Header text on MiniCalendar
- **MiniCalendar Time**: Time display on MiniCalendar
- **Full Calendar Header**: Header on the full calendar view
- **Chat Timestamp**: In-game timestamps in chat

### Format Presets

- `short`: Abbreviated format
- `long`: Standard format
- `full`: Complete format with all details
- `ordinal`: Day with ordinal suffix
- `fantasy`: Fantasy-style descriptive format
- `time`: 24-hour time
- `time12`: 12-hour time with AM/PM
- `approxTime`: Approximate time of day
- `approxDate`: Approximate date
- `datetime`: Date and time combined
- `datetime12`: Date and 12-hour time
- `custom`: User-defined format string

### Format Tokens

Date tokens: `YYYY`, `YY`, `MMMM`, `MMM`, `MM`, `M`, `DD`, `D`, `Do`, `dddd`, `ddd`

Time tokens: `HH`, `H`, `hh`, `h`, `mm`, `A`, `a`

Fantasy tokens: `[approxTime]`, `[approxDate]`, `[moon]`, `[era]`, `[eraAbbr]`, `[season]`, `[seasonAbbr]`, `[ch]`, `[chAbbr]`

Cycle tokens: `[cycle]`, `[cycleName]`, `[cycleRoman]`

**Note:** For monthless calendars, month-related tokens return empty strings.

---

## Macros (GM Only)

### Global Triggers

Assign macros to run at specific times:

- **Dawn**: Sunrise
- **Dusk**: Sunset
- **Midday**: Noon
- **Midnight**: Midnight
- **New Day**: Day change

### Season Triggers

Assign macros to run when specific seasons begin. Supports "All Seasons" for any season change.

### Moon Phase Triggers

Assign macros to run on specific moon phases. Configure by moon and phase, or use "All Moons"/"All Phases" wildcards.

---

## Chat (GM Only)

### Chat Timestamp Mode

How to display in-game time on chat messages.

- `disabled`: No in-game timestamps
- `replace`: Replace real-world time with in-game time
- `augment`: Show both real and in-game time
- Default: `disabled`

### Show Time in Timestamps

Include hours/minutes in chat timestamps.

- Default: `true`

---

## Advanced

### Primary GM (GM Only)

Designate which GM controls time advancement in multi-GM games.

- Default: Auto (first active GM)

### Logging Level

Control console debug output.

- `Off`: No logging
- `Errors`: Only errors
- `Warnings`: Errors and warnings
- `Verbose`: All debug information
- Default: `Warnings`

### Dev Mode (GM Only)

Enable developer features such as calendar journal deletion.

- Default: `false`

---

## Calendaria HUD

### Show on World Load

Display the Calendaria HUD when the world loads.

- Default: `false`

### HUD Mode

- `Fullsize`: Full HUD display with dome/slice dial
- `Compact`: Condensed bar display (forces slice dial)
- Default: `fullsize`

### Dial Style

Choose how the sun/moon are displayed:

- `Dome`: Semi-circular dome above the bar with sun/moon arc
- `Slice`: Horizontal strip in the bar with sun/moon traveling left-to-right
- Default: `dome`

### Compact During Combat

Automatically switch to slice style during combat to reduce screen space.

- Default: `true`

### Block Visibility

Toggle visibility of indicator blocks in the HUD bar:

- **Show Weather**: Display weather indicator
- **Show Season**: Display season indicator
- **Show Era/Cycle**: Display era and cycle indicators

Hiding blocks automatically shrinks HUD width. Settings are user-scoped (each player can customize their view).

### Weather Display Mode

- `Full`: Icon + label + temperature
- `Icon + Temperature`: Icon and temp only
- `Icon Only`: Just the weather icon
- `Temperature Only`: Just the temperature
- Default: `full`

### Season Display Mode

- `Icon + Text`: Both icon and season name
- `Icon Only`: Just the season icon
- `Text Only`: Just the season name
- Default: `icon + text`

### Enable Sticky Zones

Allow HUD to snap to predefined positions when dragging:

- `top-center`: Centered at top of viewport
- `above-hotbar`: Above the macro hotbar
- `above-players`: Above the players list
- `below-controls`: Below the scene controls
- Default: `true`

### Custom Time Jumps

Configure custom time jump buttons per increment (e.g., skip 8 hours). Each increment can have its own jump values.

### Sticky Tray

Remember tray open/closed state between sessions.

- Default: `false`

### Lock Position

Prevent dragging the HUD.

- Default: `false`

### Reset Position

Button to reset HUD to default position.

---

## MiniCalendar

### Show on World Load

Display the MiniCalendar when the world loads.

- Default: `true`

### Controls Delay

Seconds before auto-hiding controls after hover.

- Range: 1-10 seconds
- Default: `3`

### Sticky Time Controls

Remember time controls visibility state.

- Default: `false`

### Sticky Sidebar

Remember sidebar visibility state.

- Default: `false`

### Lock Position

Prevent dragging the MiniCalendar.

- Default: `false`

### Reset Position

Button to reset position to default.

---

## TimeKeeper

### Show on World Load

Display the TimeKeeper HUD when the world loads.

- Default: `false`

### Custom Time Jumps

Configure custom time jump buttons per increment. Each increment can have its own forward/reverse jump values.

### Date Format

- `Off`: Hide date display entirely
- Other presets: Standard format options
- Default: `short`

### Reset Position

Button to reset position to default.

---

## Per-Scene Settings

Override global settings on individual scenes via **Scene Configuration > Ambiance**:

### Darkness Sync Override

- `Use Global`: Follow the module setting
- `Enabled`: Always sync this scene
- `Disabled`: Never sync this scene
