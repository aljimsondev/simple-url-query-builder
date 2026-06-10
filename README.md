# URL Query Builder

A lightweight, zero-dependency HTML tool for constructing, inspecting, and copying URLs with query parameters. Built for developers and QA engineers who frequently work with API endpoints, redirects, or any URL that relies on query strings.

---

## Features

- **Base URL input** — paste any URL as the starting point
- **Dynamic param rows** — add as many key/value pairs as needed; each is an editable input
- **Remove params** — click the × button on any row to delete it instantly
- **Live URL generation** — the generated URL updates in real time as you type; no submit button needed
- **Color-coded output** — base URL, keys, and values are highlighted in distinct colors for quick scanning
- **Three copy options:**
  - **Copy full URL** — the complete URL including origin, path, and query string
  - **Copy relative path** — path + query string only, no `https://domain` _(suggested)_
  - **Copy params only** — just the `?key=value&…` portion

---

## Usage

1. Open `url-query-builder.html` in any modern browser — no server required
2. Paste your base URL into the **Base URL** field
3. Click **Add param** to add key/value rows; fill them in
4. The generated URL appears instantly in the **Generated URL** section
5. Use one of the three copy buttons to grab what you need

---

## Copy options explained

| Option                | Output                            | When to use                           |
| --------------------- | --------------------------------- | ------------------------------------- |
| Copy full URL         | `https://example.com/api?foo=bar` | Sharing a complete link               |
| Copy relative path ⭐ | `/api?foo=bar`                    | Frontend routing, fetch calls, Axios  |
| Copy params only      | `?foo=bar`                        | Appending to an existing URL manually |

---

## File structure

```
url-query-builder.html   ← single self-contained file, open and use
README.md
```

---

## Technical notes

- **No dependencies** — no frameworks, no CDN calls, no build step
- **Single file** — all HTML, CSS, and JS are inlined
- **Dark mode** — automatically adapts via `prefers-color-scheme`
- **Encoding** — all keys and values are `encodeURIComponent`-encoded in the output
- **Existing query strings** — if the base URL already contains a `?`, additional params are appended with `&` instead of creating a duplicate `?`
- **Browser support** — works in any modern browser (Chrome, Firefox, Safari, Edge)

---

## Example

**Input**

| Field    | Value                            |
| -------- | -------------------------------- |
| Base URL | `https://api.example.com/search` |
| Param 1  | `q` = `hello world`              |
| Param 2  | `page` = `2`                     |
| Param 3  | `limit` = `20`                   |

**Output**

```
https://api.example.com/search?q=hello%20world&page=2&limit=20
```

**Relative path copy**

```
/search?q=hello%20world&page=2&limit=20
```

---

## License

Free to use and modify for personal or commercial projects.
