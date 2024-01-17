# Guide to making a text changer Chrome extension

Check out the live site [here](https://text-changer-guide.vercel.app/). The site is custom built using [Tailwind CSS](https://tailwindcss.com) and [Next.js](https://nextjs.org).

## What it is

This is a guide to making a text changer Chrome extension. It goes through the process of creating a Chrome extension that allows users to modify text displayed on web pages. It's an excellent tool for those who want to customize their web browsing experience, whether for accessibility, personalization, or just for fun.

## Getting started

If you want to run the guide itself, which is different from the extension, then you can clone this repository and run the following commands:

```bash
npm install
```
Next, run the development server:

```bash
npm run dev
```

Finally, open [http://localhost:3000](http://localhost:3000) in your browser to view the website.

## Customizing

You can start editing this guide by modifying the files in the `/src` folder. The site will auto-update as you edit these files. Go to `/src/app/docs/{your-page-name}/page.mdx` to edit the content of your page. The MDX supports all the features of [Markdoc](https://markdoc.io), including [shortcodes](https://markdoc.io/docs/shortcodes).

## Global search

This chrome extension guide includes a global search that's powered by the [FlexSearch](https://github.com/nextapps-de/flexsearch) library. It's available by clicking the search input or by using the `⌘K` shortcut.

This feature requires no configuration, and works out of the box by automatically scanning your documentation pages to build its index. You can adjust the search parameters by editing the `/src/markdoc/search.mjs` file.

## License

This site used designs and layouts from a template that is a commercial product and is licensed under the [Tailwind UI license](https://tailwindui.com/license). The rest of the code is not licensed, and you can use it however you want.

## Learn more

To learn more about the technologies used in this site template, see the following resources:

- [Tailwind CSS](https://tailwindcss.com/docs) - the official Tailwind CSS documentation
- [Next.js](https://nextjs.org/docs) - the official Next.js documentation
- [Headless UI](https://headlessui.dev) - the official Headless UI documentation
- [Markdoc](https://markdoc.io) - the official Markdoc documentation
- [Algolia Autocomplete](https://www.algolia.com/doc/ui-libraries/autocomplete/introduction/what-is-autocomplete/) - the official Algolia Autocomplete documentation
- [FlexSearch](https://github.com/nextapps-de/flexsearch) - the official FlexSearch documentation
