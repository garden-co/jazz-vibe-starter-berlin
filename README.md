# 📝 Jazz Vibe Coding Starter

This repo was created using `npx create-jazz-app@latest --example todo` and it's a clone of a minimal Todo app example [(visit this page for more examples)](https://jazz.tools/examples). Users can use this as a starter project to build on top of.

## 🚀 Getting Started

Run:

```bash
npm install
npm dev
````

Open [http://localhost:5173](http://localhost:5173) with your browser to see the result.

## 🗂️ Structure

* [`src/basicComponents`](./src/basicComponents): simple components to build the UI, unrelated to Jazz (uses [shadcn/ui](https://ui.shadcn.com))
* [`src/components`](./src/components/): helper components that do contain Jazz-specific logic, but aren't very relevant to understand the basics of Jazz and CoJSON
* [`src/1_schema.ts`](./src/1_schema.ts), [`src/2_main.tsx`](./src/2_main.tsx), [`src/3_NewProjectForm.tsx`](./src/3_NewProjectForm.tsx), [`src/4_ProjectTodoTable.tsx`](./src/4_ProjectTodoTable.tsx): the main files for this example, see the walkthrough below

## 🧭 Walkthrough

### 🔧 Main Parts

1. 🧱 Defining the data model with CoJSON: [`src/1_schema.ts`](./src/1_schema.ts)
2. 🚪 The top-level provider `<WithJazz/>` and routing: [`src/2_main.tsx`](./src/2_main.tsx)
3. 🆕 Creating a new todo project: [`src/3_NewProjectForm.tsx`](./src/3_NewProjectForm.tsx)
4. 📋 Reactively rendering a todo project as a table, adding and editing tasks: [`src/4_ProjectTodoTable.tsx`](./src/4_ProjectTodoTable.tsx)

## 🤖 Write Jazz code with LLMs

The project contains 2 agentic flows designed to assist with Jazz development:

### Available Rules

- **`generate-jazz-schema.mdc`** - Helps with generating a Jazz schema based on user input
  - Example usage: *"generate the schema for a notes app"*
  
- **`jazz-general-help.mdc`** - Provides assistance with general Jazz questions
  - Example usage: *"how do file uploads work in Jazz?"*

### Integration Options

#### With Cursor

Both rules are automatically picked up and triggered by the Cursor Agent based on your request. Simply describe what you need, and the appropriate rule will be activated.

#### With Bolt.new

1. Clone this repository in Bolt by accessing this URL [https://bolt.new/\~/github.com/garden-co/jazz-vibe-starter-berlin](https://bolt.new/~/github.com/garden-co/jazz-vibe-starter-berlin)

2. Reference a rule in your chat message:
   ```
   Use @.cursor/rules/generate-jazz-schema.mdc to generate a schema for a notes app
   ```


## 💬 Questions / Problems / Feedback

If you have feedback, let us know on [Discord](https://discord.gg/utDMjHYg42) or open an issue or PR to fix something that seems wrong.

## ⚙️ Configuration: Sync Server

By default, the example app uses [Jazz Cloud](https://jazz.tools/cloud) (`wss://cloud.jazz.tools`) – so cross-device use, invites and collaboration should just work.

You can also run a local sync server by running:

```bash
npx jazz-run sync
```

Then add the query param `?sync=ws://localhost:4200` to the URL of the example app (e.g., `http://localhost:5173/?peer=ws://localhost:4200`), or set the `sync` parameter of the `<JazzProvider>` component in [./src/2\_main.tsx](./src/2_main.tsx).
