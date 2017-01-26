---
layout: page.ejs
category: jekyll
title: Localization
position: 8
---

There is many way to handle multiple languages with Jekyll — just as an example, take a look at [this guide](https://www.sylvaindurand.org/making-jekyll-multilingual/), or [this plugin](https://github.com/vwochnik/jekyll-language-plugin). 

Just as explained in the product overview, DatoCMS is totally agnostic in terms of static site generators: it just allows you to dump content locally, and the rest is up to you.

Within your `dato.config.rb` file, you can easily switch between your administrative area locales like this:

```ruby
# dato.config.rb

I18n.locale = :en
dato.blog_posts.first.title   # => "Hello world!"

I18n.locale = :it
dato.blog_posts.first.title   # => "Ciao mondo!"
```

You can also iterate over your locales with `I18n.available_locales`:

```ruby
I18n.available_locales.each do |locale|
  I18n.with_locale(locale) do
    dato.blog_posts.first.title
  end
end
```