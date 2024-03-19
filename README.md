# jtof.dev
- welcome to the github repo for [jtof.dev](https://jtof.dev)!
- `jtof.dev` is powered by github pages through a handful of domain records (you can find the documentation for this [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)):

| type  | domain name                                     | content                            |
|-------|-------------------------------------------|----------------------------------|
| A     | jtof.dev                                  | 185.199.108.153                  |
| A     | jtof.dev                                  | 185.199.109.153                  |
| A     | jtof.dev                                  | 185.199.110.153                  |
| A     | jtof.dev                                  | 185.199.111.153                  |
| AAAA  | jtof.dev                                  | 2606:50c0:8000::153              |
| AAAA  | jtof.dev                                  | 2606:50c0:8001::153              |
| AAAA  | jtof.dev                                  | 2606:50c0:8002::153              |
| AAAA  | jtof.dev                                  | 2606:50c0:8003::153              |
| ANAME | jtof.dev                                  | jjtofflemire.github.io           |
| TXT   | `challenge subdomain`.jtof.dev | `verification code` |
| CNAME | www.jtof.dev                              | jjtofflemire.github.io           |

- as well as a `CNAME` file containing the `jtof.dev` url

## jtof.dev/cookbook
- I store all of my recipes in obsidian, in a standard markdown format
- I convert all my recipes to `html` pages with all the custom formatting using `src/main.rs`
  - this script can be called with `cargo run` from the `cookbook/` folder
  - this script also gets [automatically called](.git/hooks/pre-commit) using `git hook`'s

### jtof.dev/cookbook/src
- this folder holds the `main.rs` script, and the `.html` files that the script pulls in
  - the html headers and footers are used to cobble together html pages for each recipe

## light and dark mode
- light and dark mode is controlled by a `localStorage` javascript variable which is checked at load time
  - light and dark mode respectively set a `light-mode` or `dark-mode` class on the `<body>`
  - all the color changes are handled by css snippets that check this body class:

```
body.light/dark-mode class {
    css
}
```

## mobile view
- a section of `styles.css` checks the screen width, and applies css changes when there are less than a certain number of pixels:

```
@media screen and (max-width: 1000px) {
    class {
        css
    }
}
```

# to do
- [ ] tweak css for better theming and better mobile view
    - add padding to header and footer so that it is padded by a couple of pixels from the edges of the 800px viewbox / mobile view
  - increase mobile view size of home png, dark toggle, and search bar in `cookbook`
  - experiment with theme changes
    - take more inspiration from the [gruvbox light theme](https://github.com/morhetz/gruvbox)
    - try out different dark shades
- [ ] add resume page
- [ ] add an about me page (probably as part of the homepage)
- [ ] add movie and show reviews (I can reuse a lot of the code from `cookbook`, with some modified code)
