# Calendar HUD

The Calendar HUD (`CalendariaHUD`) displays date, time, weather, and events in a draggable widget. Two display modes are available: the full HUD with an animated dome (or slice), or a compact calendar view.

---

## Opening the HUD

- Press **Alt+C** to toggle visibility
- Automatically opens on world load (if enabled in settings)
- Double-click the MiniCalendar to open the full calendar

---

## HUD Mode

Configured via Settings > HUD tab:

| Mode | Description |
|------|-------------|
| `full` | Animated sky view with sun/moon arc and info bar |
| `compact` | Condensed bar with slice dial (no dome) |

Double-click the HUD bar to toggle between fullsize and compact modes.

---

## Dial Styles

The HUD supports two dial styles for displaying the sun/moon:

| Style | Description |
|-------|-------------|
| `dome` | Semi-circular dome above the bar with sun/moon arc |
| `slice` | Horizontal strip in the bar with sun/moon traveling left-to-right |

Configure via Settings > HUD tab > Dial Style.

### Combat Auto-Compact

When enabled (default ON), the HUD automatically switches to slice style during combat to reduce screen space usage. Configure via Settings > HUD tab > Compact During Combat.

---

## Full HUD

### Dome Display

The dome shows a dynamic sky that changes based on time of day:

- Sky gradient interpolates between 15 keyframes (0:00-24:00)
- Sun visible between hours 6-18; moon visible outside this range
- Stars fade in/out during twilight (5:30-7:00 and 17:30-19:00)
- Clouds visible during daylight (7:00-18:00)

**GM Only**: Click the dome to open the Time Dial for quick time adjustments.

**Players**: The dome is view-only and cannot be clicked.

### Time Dial (GM Only)

Click the dome or slice to open the Time Dial overlay:

- Drag the sun/moon around the arc to set time visually
- Time updates in real-time as you drag
- Release to confirm the new time
- Click outside or press Escape to cancel

### Slice Display

An alternative to the dome showing a horizontal sky strip:

- Sun/moon travels left-to-right across the bar
- Time displayed over the sky gradient
- Automatically used in compact mode

### Info Bar

The bar displays (left to right):

- **Search button** - Opens note search panel
- **Add Note button** - Creates a new note for today
- **Date** - Click to open Set Date dialog (GM only)
- **Events** - Icons for today's notes (up to 5); click to open note
- **Time** - Current time with play/pause button (GM only)
- **Weather** - Current weather; click to open weather picker (GM only)
- **Season** - Current season name and icon
- **Era** - Current era indicator
- **Cycle** - Current cycle value (if configured)
- **Open Calendar** - Opens the full calendar application
- **Settings** - Opens the settings panel

### Block Visibility

Each indicator block (weather, season, era/cycle) can be hidden via Settings > HUD tab. Hiding blocks shrinks the HUD width automatically.

**Weather Display Modes:**

- Full (icon + label + temperature)
- Icon + Temperature
- Icon Only
- Temperature Only

**Season Display Modes:**

- Icon + Text
- Icon Only
- Text Only

Settings are user-scoped - each player can customize their view.

### Time Controls Tray (GM Only)

Hover over the bar to reveal time controls:

| Button | Action |
|--------|--------|
| Sunrise | Advance to sunrise |
| Midday | Advance to solar noon |
| Reverse | Step backward by increment |
| Increment dropdown | Set step size (second, round, minute, hour, day, week, month, season, year) |
| Forward | Step forward by increment |
| Sunset | Advance to sunset |
| Midnight | Advance to midnight (next day) |

**Note:** Real-time clock speed is configured in Settings > Time tab, not on the HUD.

### Custom Time Jumps

Configure custom jump buttons (e.g., skip 8 hours) via Settings > HUD tab > Custom Time Jumps. Each increment can have its own jump values.

---

## MiniCalendar

A mini month view with integrated time controls.

### Navigation

- **Arrow buttons** - Previous/next month (or week for monthless calendars)
- **Today button** - Return to current date
- Click a day to select it
- Click a grayed-out day to navigate to that month

### Monthless Calendars

For calendars without months (like Traveller), the MiniCalendar shows a 3-week view:

- Previous week, current week, and next week
- Navigation moves by week instead of month
- Header displays "Week X, Year"

### Day Cells

Each day cell may show:

- Note count badge (if notes exist)
- Festival highlight
- Moon phase icon
- Today indicator
- Selected indicator

### Sidebar

Appears on hover (or when sticky):

- Close
- Open Full Calendar
- Today
- Set Current Date (when a date is selected, GM only)
- Add Note
- Search Notes
- View Notes (when notes exist on selected date)
- Settings

### Notes Panel

Click "View Notes" to see all notes for the selected date:

- Notes sorted by time (all-day first)
- Click a note to open in view mode
- Click edit icon to open in edit mode (if owner)

### Time Display

Shows current time. GM can:

- Click to toggle time flow (play/pause)
- Hover to reveal time controls

### Time Controls (GM Only)

Revealed on hover:

- Sunrise, Midday shortcuts
- Reverse 5x, Reverse
- Increment selector
- Forward, Forward 5x
- Sunset, Midnight shortcuts

### Double-Click Behavior

- Double-click MiniCalendar to open the full Calendar Application
- Double-click the full Calendar Application to return to MiniCalendar

---

## Clock Sync

The real-time clock syncs with game state:

- **Pause Sync**: Clock stops when game is paused, resumes at 1:1 when unpaused
- **Combat Sync**: Clock stops during combat (time advances per-turn via system)

When sync is enabled and blocked (paused or in combat), manually starting the clock shows a warning notification.

Configure sync behavior in Settings > Time tab.

---

## Search

Both HUD modes include a search panel:

- Type at least 2 characters to search note names and content
- Click a result to open the note
- Press **Escape** to close

---

## Positioning

### Dragging

- **Full HUD**: Drag the info bar
- **MiniCalendar**: Drag the top row (month/year header)

Position is saved per-client.

### Sticky Zones

Drag the HUD near predefined zones for automatic snapping:

| Zone | Location |
|------|----------|
| `top-center` | Centered at top of viewport |
| `above-hotbar` | Above the macro hotbar |
| `above-players` | Above the players list |
| `below-controls` | Below the scene controls |

When dragging into a zone, the HUD wobbles to indicate snapping will occur. Release to snap into position.

Toggle sticky zones via Settings > HUD tab > Enable Sticky Zones.

Debug visualization: `game.calendaria.showDebugZones()` or enable Dev Mode.

### Dome Visibility (Full HUD)

The dome automatically fades when approaching the top of the viewport and hides entirely if insufficient space.

### Locking Position

Enable "Lock Position" in settings to prevent dragging.

### Resetting Position

Settings > HUD tab (or MiniCalendar tab) > Reset Position

---

## TimeKeeper HUD

A minimal time-only display for GMs who want a smaller footprint.

### Features

- Fixed compact width
- Controls hidden on idle, revealed on hover
- Play/pause as hover overlay on time display
- Right-click for context menu (Settings, Close)
- Configurable time jump buttons per increment
- "Off" format option to hide date display

### Controls

Hover to reveal:

- Reverse/Forward buttons
- Increment selector

Configure jump buttons via Settings > TimeKeeper tab.

---

## Settings Summary

### HUD Tab

| Setting | Description |
|---------|-------------|
| Show Calendar HUD | Display on world load |
| HUD Mode | `fullsize` or `compact` |
| Dial Style | `dome` or `slice` |
| Compact During Combat | Auto-switch to slice in combat |
| Show Weather | Display weather indicator |
| Weather Display Mode | full/icon+temp/icon-only/temp-only |
| Show Season | Display season indicator |
| Season Display Mode | icon+text/icon-only/text-only |
| Show Era/Cycle | Display era and cycle indicators |
| Enable Sticky Zones | Allow snapping to predefined positions |
| Sticky Tray | Keep controls visible |
| Lock Position | Prevent dragging |
| Reset Position | Reset to default |

### MiniCalendar Tab

| Setting | Description |
|---------|-------------|
| Show MiniCalendar | Display on world load |
| Controls Delay | Seconds before auto-hide (1-10s) |
| Sticky Time Controls | Keep time controls visible |
| Sticky Sidebar | Keep sidebar visible |
| Lock Position | Prevent dragging |
| Reset Position | Reset to default |

### TimeKeeper Tab

| Setting | Description |
|---------|-------------|
| Show TimeKeeper | Display on world load |
| Custom Time Jumps | Configure jump buttons per increment |
| Reset Position | Reset to default |

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Alt+C | Toggle HUD visibility |
| Escape | Close search panel |

---

## Player Permissions

Players have limited HUD interaction:

- **Can**: View date/time/weather, search notes, view non-GM notes, create notes
- **Cannot**: Open Set Date dialog, change time, change weather, access time controls

The dome and all time-related controls are non-interactive for players.
