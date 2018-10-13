## Custom

`image.html` - an include that provides `figure` and `figcaption` html markup.

Keep an eye on this issue that will make this snippet obsolete: https://github.com/gettalong/kramdown/issues/48

Usage

```
{% include image.html
  url="/assets/images/posts/a21a/try-the-api-nlp.jpg"
  alt="Screenshot of sentiment analysis results"
  caption="Sentiment analysis results indicate a score of .7 and magnitude of 1.5" %}
```
