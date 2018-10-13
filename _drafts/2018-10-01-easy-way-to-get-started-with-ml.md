---
title: Natural Language API, APIs Explorer and AutoML — no code
categories: [machine learning]
---

Alternate titles:

- The non technical way to getting started with Google's machine learning APIs
- No code machine learning with Google APIs

Let's look at different ways we can try the AI and machine learning APIs (application program interface) availabe in the Google Cloud Platform. For example, if we go to the [Cloud Natural Language product page](https://cloud.google.com/natural-language/){:target="\_blank"} there's a "Try the API" tool directly on the page. Right away, we can type in some text and analyze it.

For fun, try bits of email messages you've sent to friends or colleagues. Do you think they were perceived positively...negatively? What does the sentiment analysis say?

Let's plug in the following message into the tool and navigate to the **Sentiment** tab...

> No worries, we can connect next week. Have a great weekend!

![Screenshot of sentiment analysis results](/assets/images/posts/a21a/try-the-api-nlp.jpg)
<small class="figcaption">Sentiment analysis results indicate a score of .7 and magnitude of 1.5</small>

Take a moment to study the output. The tool broke out and listed the sentences contained in the message and assigned them some numbers.

The `score` gives us a sense of the overall emotion of a message — between `1` (positive emotion) and `-1` (negative emotion). It doesn't tell us if the emotion is happy, sad or mad. That's up to us to decide. The `magnitude` indicates how much emotional content is present within the message — between `0` and any positive number — and is generally proportional to the message length. Emails tend to be short so we wouldn't expect this value to climb very high.

_For a deeper explanation of how sentiment is represented by the `score` and `magnitude` values, see [Interpreting sentiment analysis values](https://cloud.google.com/natural-language/docs/basics#interpreting_sentiment_analysis_values){:target="\_blank"}._

Based on the results, I'd say our message would be regarded in a clearly positive light. But, someone else might disagree. It's possible that the threshold for what's considered clearly positive is different from what we come up with, and that's ok.

## APIs Explorer

Another way we can dig into the Cloud Natural Language (CNL) API is with the [APIs Explorer](https://developers.google.com/explorer-help){:target="\_blank"} — a tool that helps us explore various Google APIs interactively.

![Screenshot of APIs Explorer home page](/assets/images/posts/a21a/apis-explorer.png)
<small class="figcaption">The APIs Explorer lists the majority of APIs offered by Google</small>

{% include image.html
  url="/assets/images/posts/a21a/apis-explorer.png"
  alt="Screenshot of the APIs Explorer home page"
  caption="The APIs Explorer lists the majority of APIs offered by Google" %}

As a beginner, the UI is daunting compared to the friendly layout of the product page tool and it's not clear what to do next. But, not all APIs will have a fancy UI counterpart. Also, with the APIs Explorer, we can play with every switch and dial that an API has. For instance, instead of typing text into an input box as we did before, a body of text can be stored as a file in Google Cloud Storage and fed to the CNL API. This option isn't available in the product page tool.

[Open the browser to the sentiment analysis](https://developers.google.com/apis-explorer/#p/language/v1/language.documents.analyzeSentiment){:target="\_blank"} section of the CNL API. Click into the request body. With the dropdowns, add the `document` property. Then, under the document property, add the `content` property and enter the message to analyze. Finally, add the `type` property and enter "PLAIN_TEXT" (without the quotes).

![Screenshot of request body filled in with the document, content and type properties added](/assets/images/posts/a21a/apis-explorer-request-body-filled.png)
<small class="figcaption">Request body filled in with the document, content and type properties added</small>

At a minimum, a `document` with `content` and `type` properties should be entered into the request body before the execute button is pressed.

Ok, if this is the first time you're executing the request, the button will read as **Authorize and execute**. When you press it, Google will ask you to sign in with your account. Otherwise, it'll just read as **Execute**.

After executing the request, check down in the **Response** section to see the results of the analysis. Have a close look at the `score` and `magnitude` properties. Assuming we used the same content from the first example, the numbers will be the same.

![Screenshot of sentiment analysis results in JSON format](/assets/images/posts/a21a/apis-explorer-response.png){:style="max-width: 471px"}
<small class="figcaption">Sentiment analysis results indicate a score of .7 and magnitude of 1.5</small>

## Next steps

Give the [Cloud Vision API](https://cloud.google.com/vision/) a go. Just like the Cloud Natural Language API, you can [try the Cloud Vision API from the product page](https://cloud.google.com/vision/). It only allows for uploading a photo from the desktop. If you don't have a particularly interesting photo already, download some from the internet first. Or, if you [head over to the Cloud Vision API in the API Explorer](Cloud Vision API in the API Explorer), more options are available.

Can a photo be provided by URL? Here's a hint — with the important bits highlighted...

![Screenshot of Cloud Vision request body](/assets/images/posts/a21a/apis-explorer-vision-filled.png)
<small class="figcaption">Request body for Cloud Vision</small>

## AutoML

<iframe width="600" height="350" src="https://datastudio.google.com/embed/reporting/1qqluijwur766ABJQvz1bWsmGRsQV37kE/page/vy0Z" frameborder="0" style="border:0" allowfullscreen></iframe>
