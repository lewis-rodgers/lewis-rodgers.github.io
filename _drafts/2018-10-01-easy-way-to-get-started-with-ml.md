---
title: No code machine learning with Google ML APIs
categories: [machine learning]
notes: https://www.evernote.com/shard/s3/nl/196239/de369a32-99cb-4c46-8e50-dc339ecab17d/
---

Alternate titles:

- The non technical way to getting started with Google's machine learning APIs
- No code machine learning with Google APIs
- No code machine learning with the Cloud Natural Language API and APIs Explorer
- Natural Language API, APIs Explorer and AutoML — no code

There are a few different ways we can try the AI and machine learning APIs availabe from Google Cloud. All of which don't require any code.

1. "Try the API" tool - The lowest barrier to entry. These can be found on some of the product pages at [https://cloud.google.com](https://cloud.google.com).
2. APIs Explorer - Similiar to the "Try the API" tool, but more developer focused and without the fancy UI.
3. AutoML

_There can a bit of setup involved with AutoML so this post will only cover the first two on the list._

## 1. Try the API

If we go to the [Cloud Natural Language product page][1] a "Try the API" tool can be found directly on the page. Right away, we can type in some text, analyze it and see the results.

For fun, try bits of email messages you've sent to friends or colleagues. Do you think they were perceived positively...negatively? What does the sentiment analysis say?

Plug in the following message into the tool and navigate to the **Sentiment** tab...

> No worries, we can connect next week. Have a great weekend!

![Sentiment analysis results indicate a score of .7 and magnitude of 1.5][image-1]

The tool broke out and listed the sentences contained in the message and assigned them some numbers.

The `score` gives us a sense of the overall emotion of a message — between `1` (positive emotion) and `-1` (negative emotion). It doesn't tell us if the emotion is happy, sad or mad. That's up to us to decide.

The `magnitude` indicates how much emotional content is present within the message — between `0` and any positive number — and is generally proportional to the message length. Emails tend to be short so we wouldn't expect this value to climb very high.

_For a deeper explanation of how sentiment is represented by the `score` and `magnitude` values, see [Interpreting sentiment analysis values][2]._

These machine learning APIs also come with a "Try the API" tool:

- [Cloud Vision](https://cloud.google.com/vision/)
- [Cloud Translation](https://cloud.google.com/translate/)
- [Cloud Video Intelligence](https://cloud.google.com/video-intelligence/)
- [Cloud Speech-to-Text](https://cloud.google.com/speech-to-text/)
- [Cloud Text-to-Speech](https://cloud.google.com/text-to-speech/)

## 2. APIs Explorer

Another way we can dig into the Cloud Natural Language (CNL) API is with the [APIs Explorer][3] — a tool that helps us explore various Google APIs interactively.

![The APIs Explorer lists the majority of APIs offered by Google][image-2]

~~The API Explorer friendly layout of the product page tool and it's not clear what to do next. But, not all APIs will have a fancy UI counterpart. Also, with the APIs Explorer, we can play with every switch and dial that an API has. For instance, instead of typing text into an input box as we did before, a body of text can be stored as a file in Google Cloud Storage and fed to the CNL API. This option isn't available in the product page tool.~~

[In the CNL sentiment analysis section][4] of the APIs Explorer, click into the request body. Using the dropdown...

1. Add the `document` property.
2. Then, under the document property, add the `content` property and enter the same message from the first example.
3. Finally, add the `type` property and enter "PLAIN_TEXT" (without the quotes).

![Request body filled in with the document, content and type properties added][image-3]

~~At a minimum, a `document` with `content` and `type` properties should be entered into the request body before the execute button is pressed.~~

~~If this is the first time you're executing the request, the button will read as **Authorize and execute**. When you press it, Google will ask you to sign in with your account. Otherwise, it'll just read as **Execute**.~~

After pressing the **Authorize and execute** (or just Execute) button, check down in the **Response** section to view the results of the analysis. See the `score` and `magnitude` properties? Assuming we used the same message from the first example, the numbers match.

![Sentiment analysis results indicate a score of .7 and magnitude of 1.5][image-4]{:style="max-width: 471px"}

## Next steps

Give the Cloud Vision API a go. Just like the Cloud Natural Language API, you can [try the Cloud Vision API from the product page][vision].

Then, use the APIs Explorer to discover more features and options. Like providing a photo with a URL instead of uploading one.

![Request body for Cloud Vision][image-5]

[1]: https://cloud.google.com/natural-language/
[2]: https://cloud.google.com/natural-language/docs/basics#interpreting_sentiment_analysis_values
[3]: https://developers.google.com/explorer-help
[4]: https://developers.google.com/apis-explorer/#p/language/v1/language.documents.analyzeSentiment
[vision]: https://cloud.google.com/vision/
[image-1]: /assets/images/posts/a21a/try-the-api-nlp.jpg "Screenshot of sentiment analysis results"
[image-2]: /assets/images/posts/a21a/apis-explorer.png "Screenshot of APIs Explorer home page"
[image-3]: /assets/images/posts/a21a/apis-explorer-request-body-filled.png "Screenshot of request body filled in with the document, content and type properties added"
[image-4]: /assets/images/posts/a21a/apis-explorer-response.png "Screenshot of sentiment analysis results in JSON format"
[image-5]: /assets/images/posts/a21a/apis-explorer-vision-filled.png "Screenshot of Cloud Vision request body"
