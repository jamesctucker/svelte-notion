# Svelte Notion

An unofficial Notion API tool set for Svelte & Sapper

This package uses https://github.com/splitbee/notion-api-worker to generate the API. You can host this yourself, but OOTB it uses https://notion-api.splitbee.io/

This package is very experimental and subject to change. Check out a working page here: https://www.scotttolinski.com/notion

## How To Use

`npm install @leveluptuts/svelte-notion`

```

<script context="module">
  import { Notion, fetchNotion } from "@leveluptuts/svelte-notion";

  export async function preload() {
    const pageId = `3e03212e646e41caaa560408162dee99`;
    const blocks = await fetchNotion({ id: pageId, context: this });
    return { blocks };
  }
</script>

<script>
  export let blocks;
</script>

<Notion {blocks} />

```

## What's supported currently

(shout-out to splitbee for this dope table. I borrowed from his React Notion repo)

We happily accept pull requests to add support for the missing blocks. I'll be adding as many as I can asap.

| Block Type        | Supported  | Notes                |
| ----------------- | ---------- | -------------------- |
| Text              | ✅ Yes     |                      |
| Heading           | ✅ Yes     |                      |
| Image             | ❌ Missing |                      |
| Image Caption     | ❌ Missing |                      |
| Bulleted List     | ❌ Missing |                      |
| Numbered List     | ❌ Missing |                      |
| Quote             | ❌ Missing |                      |
| Callout           | ❌ Missing |                      |
| Column            | ❌ Missing |                      |
| iframe            | ❌ Missing |                      |
| Video             | ❌ Missing | Only embedded videos |
| Divider           | ❌ Missing |                      |
| Link              | ❌ Missing |                      |
| Code              | ✅ Yes     |                      |
| Web Bookmark      | ❌ Missing |                      |
| Databases         | ❌ Missing |                      |
| Checkbox          | ❌ Missing |                      |
| Toggle List       | ❌ Missing |                      |
| Table Of Contents | ❌ Missing |                      |

## How To Host Your Own API

Coming Soon

## FAQ

### Is this practical?

Maybe? I could be much more very soon.

### I thought Notion didn't have an API?

It don't. Don't hold your breath on this working for ever. See the Splitbee package for more info. The intention would be to migrate this to the official API once it's released.

## Credits

Heavily inspired by https://github.com/splitbee/react-notion
