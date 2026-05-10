# Webring for BCH

A modern implementation of webrings for the Bitcoin Cash community, bringing back a beloved web tradition with contemporary technology.

## What are Webrings?

[Webrings](https://wikis.fandom.com/wiki/WebRings) are a curated collection of websites linked together in a ring structure, allowing users to navigate from one site to the next in the same community or interest group.

### Historical Context

Before search engines became dominant, webrings served as a crucial discovery mechanism on the web. In the 1990s and early 2000s, they provided:

- **Community building**: Sites with shared interests were grouped together, creating mini-communities around niche topics
- **Discovery**: Users could "hop" through related sites without relying on centralized search engines
- **Quality curation**: Ring administrators vetted sites before inclusion, ensuring quality content within each ring
- **Decentralization**: An alternative to the "top-down" content approach that larger platforms provided

At their peak, there were 20+ webring providers and approximately 80,000 different rings. However, the rise of Google and other search engines, combined with the acquisition and mismanagement of major ring services (notably Yahoo's acquisition of WebRing.org), led to their decline.

### Why Revive Webrings?

Webrings are experiencing a revival because:

- The modern web is increasingly centralized around a few large platforms and social media sites
- Many independent creators and developers want to connect directly with each other rather than through algorithmic feeds
- They provide an alternative to SEO-driven discovery and algorithm-based recommendations
- They represent a return to the philosophy of an open, community-driven web

## This Implementation

This project implements a modern webring using Web Components, making it easy for Bitcoin Cash community websites to participate with minimal setup.

A `<bch-webring>` Web Component — pure JavaScript, no dependencies. Site data lives in `webring.json` in this repo; the Shadow DOM keeps its styles isolated from the host page. Sites join via pull request, navigate via prev/next/random links rendered by the component.

### Getting Started

#### For Site Owners

1. Submit a pull request adding your site to [`webring.json`](./webring.json) (see the data structure below).

2. Load the script and add the element to your page:

   ```html
   <link
     rel="stylesheet"
     href="https://raw.githubusercontent.com/BitcoinCash1/css-webring/main/webring.css"
   />
   <script src="https://raw.githubusercontent.com/BitcoinCash1/css-webring/main/webring.js"></script>

   <bch-webring site="https://yourdomain.com"></bch-webring>
   ```

   Or omit the stylesheet and style the element yourself in your own CSS:

   ```css
   bch-webring {
     display: block;
     max-width: 450px;
     margin: 1rem auto;
   }
   ```

> ![INFO]
> **Prefer not to load remote scripts?** You can copy [`webring.js`](./webring.js) directly into your project and serve it yourself. The file has no dependencies — just host it anywhere and point your `<script src="...">` at your own local copy.

---

Example screenshot when deployed:

![Screenshot](./example_screen.png)

#### Data structure (JSON)

The [`webring.json`](./webring.json) file is a flat array of site objects:

```json
[
  {
    "url": "https://example.com",
    "name": "Example Site",
    "owner": "Jane Doe"
  }
]
```

Each entry requires `url`, `name`, and `owner`. Add your site by opening a pull request that appends your entry to the array.

## Contributing

We welcome contributions in the following ways:

1. **Submit Your Site**: Add your Bitcoin Cash-related website to the webring via pull request
2. **Report Issues**: Found a bug or have a feature suggestion? Open an issue
3. **Improve the Code**: Pull requests for improvements, optimizations, and new features

## Project Goals

- Create a decentralized, community-maintained directory of Bitcoin Cash websites
- Demonstrate that the webring model can work effectively in the modern web
- Build an easy-to-use implementation that requires minimal setup for participating sites
- Foster discovery and community connection within the Bitcoin Cash ecosystem

## License

See [LICENSE](LICENSE) for details.

## Resources

- [Webring on Fandom](https://wikis.fandom.com/wiki/WebRings)
