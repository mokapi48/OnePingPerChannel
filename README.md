# OnePingPerChannel

A Vencord plugin that limits notifications: you only get **one alert (sound + visual)** per conversation, even if several messages or mentions arrive in a row.

Works for:
- Direct Messages (DMs)
- Group DMs
- Servers

Based on the [OnePingPerDM plugin](https://github.com/Vendicated/Vencord/tree/main/src/plugins/onePingPerDM).

## Installation

### Requirements

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/)
- [pnpm](https://pnpm.io/installation) (`npm install -g pnpm` if you don't have it)
- Discord Desktop closed during the inject step (step 5)

### Step 1 — Clone the Vencord repo

Open a terminal wherever you want the project, then:

```bash
git clone https://github.com/Vendicated/Vencord
```

This creates a `Vencord` folder with all the source code.

### Step 2 — Add the plugin

Go to the plugins folder:

```
Vencord\src\plugins\
```

Create a new folder named exactly after the plugin:

```
Vencord\src\plugins\OnePingPerChannel\
```

Put the `index.ts` file inside it:

```
Vencord\src\plugins\OnePingPerChannel\index.ts
```

### Step 3 — Install dependencies

Open a terminal **at the root of the project** (the `Vencord` folder), and run:

```bash
pnpm install --frozen-lockfile
```

This downloads everything Vencord needs to run.

### Step 4 — Build the project

Still in the same terminal:

```bash
pnpm build
```

This compiles Vencord **with your plugin included**.

### Step 5 — Inject into Discord

Close Discord Desktop, then run:

```bash
pnpm inject
```

Follow the on-screen instructions (choose Discord, Discord Canary, PTB, etc. depending on your version).

### Step 6 — Check that it works

1. Restart Discord.
2. Go to **Discord Settings → Vencord → Plugins**.
3. Look for `OnePingPerChannel` in the list and enable it.

If you can see it and enable it, the installation worked ✅

### Notes

- If you edit `index.ts` later, you need to redo **Step 4** (`pnpm build`) for changes to apply. No need to redo `pnpm inject` every time, unless Discord was updated or uninjected.
- The exact Vencord folder path depends on where you cloned it — adjust it if needed.
