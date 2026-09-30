# Ruibin Min · Academic Homepage

A responsive academic homepage for Ruibin Min, built with Jekyll and ready for GitHub Pages.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000/`.

## Main content files

- `_config.yml`: site title, short bio, avatar, and future social links.
- `_pages/includes/intro.md`: biography and research introduction.
- `_pages/includes/news.md`: recent updates.
- `_pages/includes/educations.md`: education history.
- `_pages/includes/experience.md`: research experience.
- `_pages/includes/pub.md`: selected publications.
- `_pages/includes/honers.md`: awards. The filename is retained for compatibility with the source theme.
- `_pages/includes/visitor_insights.md`: privacy-conscious local visit counter and opt-in public IP display.
- `_pages/includes/contact.md`: email, GitHub, and WeChat contact details.
- `images/avatar-placeholder.svg`: replace this file, or change `author.avatar` in `_config.yml`, when a portrait is ready.

## GitHub Pages deployment

Push this repository to `UIOSN/UIOSN.github.io` on the `main` branch. GitHub Pages can build the Jekyll site directly at `https://uiosn.github.io/`.

## Credits

This site is adapted from [AcadHomepage](https://github.com/RayeRen/acad-homepage.github.io) and [Zhenlong Yuan's homepage](https://github.com/ZhenlongYuan/zhenlongyuan.github.io), under the MIT License. Institution and company marks remain the property of their respective owners.
