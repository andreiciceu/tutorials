# Intro
Seo is an important part if you want your website to get users & show well in search engines. Here are some tips:
- https://www.youtube.com/watch?v=-B58GgsehKQ&feature=youtu.be
- rule 1 & t for seo is, create meaningful content


# Meta tags
Use `<SEOMeta>` component for setting meta-data for the current page, generated metadata will be added to `<head>` automatically.
```tsx
<SEOMeta
    title="The title" // 40-60 characters
    description="Relevant description" // max 160 characters
    keywords="one,two" // comma separated
    og={{ // open-graph properties
        title: "The og title", // 40-60, if not provided, title is used
        descritpion: "The og descritpion", // 2-4 sentences, if not provided, descritpion is used
        type: 'website' || 'article', // default website
        image: 'https://the.domain/url.png', // absolute URL
        url: 'https://the.domain/resource/url', // the resource absolute URL
    }}
/>
```
- https://ahrefs.com/blog/open-graph-meta-tags/

# Strucutred data
Markup used by search engines to know how to present data
## Global attributes
```html
<div itemscope itemtype="http://schema.org/Movie">
  <h1 itemprop="name">Avatar</h1>
  <span>Director: <span itemprop="director">James Cameron</span> (born August 16, 1954)</span>
  <span itemprop="genre">Science fiction</span>
  <a href="https://youtu.be/0AY1XIkX7bY" itemprop="trailer">Trailer</a>
</div>
```
- https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemscope

## JsonLD
Use `<SEORichSnippet>` component, generated script will be added to `<head>` automatically
```tsx
<SEORichSnippet
    item={{
        '@type': 'Person',
        name: 'Grace Hopper',
        alternateName: 'Grace Brewster Murray Hopper',
        alumniOf: {
          '@type': 'CollegeOrUniversity',
          name: ['Yale University', 'Vassar College'],
        },
        knowsAbout: ['Compilers', 'Computer Science'],
    }}
/>
```
- https://developers.google.com/search/docs/data-types/article
- https://developers.google.com/search/docs/guides/intro-structured-data
- https://backlinko.com/hub/seo/snippets
