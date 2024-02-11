---
created: 2024-02-11T01:44:11 (UTC +03:00)
tags: []
source: https://medium.com/@arjunprakash027/understanding-cosine-similarity-a-key-concept-in-data-science-72a0fcc57599
author: Arjun Prakash
---

### Unlocking the Power of Cosine Similarity: A Comprehensive Guide to Understanding and Using this Essential Data Science Metric | Medium


## Measuring similarity between 2 vectors

## Normal way

The traditional method for quantifying the distance between two points involves a direct measurement of the separation between them, a concept known as Euclidean distance measurement. This approach, named after the ancient Greek mathematician Euclid, who pioneered geometry, employs the formula √((x₁ — x₂)² + (y₁ — y₂)²) to compute the distance between two points in a two-dimensional space.

Euclidean distance isn’t limited to two dimensions; it extends naturally to three-dimensional and higher-dimensional spaces by adding more terms to the formula. In higher dimensions, it becomes √((x₁ — x₂)² + (y₁ — y₂)² + … + (z₁ — z₂)²).

## The sexy and accurate way

The contemporary and intriguing approach to measuring the proximity between two points involves the application of a concept known as cosine similarity. Cosine similarity operates by mapping vectors within a graphical context and then calculating the angle between these vectors, ultimately delivering the cosine of that angle as a measure of their similarity. When the angle between two vectors is precisely 45 degrees, their similarity is represented as cos(45).

Cosine similarity boasts an intuitive interpretation. When two vectors exhibit substantial similarity, their angle is close to 0 degrees, leading to a cosine similarity value of 1. Conversely, as the vectors become dissimilar or distant, the angle between them approaches 90 degrees, resulting in a cosine similarity value of 0. This intuitive interpretation simplifies the understanding of similarity metrics.

Furthermore, cosine similarity is remarkably versatile. It can be applied not only to pairs of points but also to a diverse array of data types, including text documents, images, and numerical data. This versatility renders cosine similarity a powerful tool in various domains, such as natural language processing, recommendation systems, and data clustering.

## Example Demonstration

Consider there are 2 sentences.

**sentence 1**: _hello world_

**sentence 2**: _hello hello_

mapping them to vector, it will be something like this

![](https://miro.medium.com/v2/resize:fit:875/1*tmK1b7qogmOfrRfVuFlk9w.jpeg)

this would look like this on graph

![](https://miro.medium.com/v2/resize:fit:875/1*6j-bkEfoq1o--xeZVljGjQ.jpeg)

**Now applying Euclidian distance formula to this,**

![](https://miro.medium.com/v2/resize:fit:875/1*oB-dT7Y0nxjalR1XtJt_DQ.jpeg)

root of 2 is around 1.4142

**Now applying cosine similarity to this**

![](https://miro.medium.com/v2/resize:fit:875/1*blPI3vLXw0Uet7wLQceYgA.jpeg)

applying formula

![](https://miro.medium.com/v2/resize:fit:875/1*OUSRS45aLU9SXxFe6tozqg.jpeg)

this is the same even if sentence 2 is hello hello hello

![](https://miro.medium.com/v2/resize:fit:875/1*1n6OdndFLpf1qeNX1A25_Q.jpeg)

while Euclidean distance will give you the value 2.2361 but cosine similarity will give you the same 0.7071

## Formula to calculate similarity for multi-dimensional arrays

The above way is an basic demonstration of cosine similarity, but in real world with text and images and other data there are no 2d vectors, they will be multi-dimensional vectors with 5 or more dimensions.

There also a formula to calculate this using cosine similarity.

> **Cosine Similarity (cos θ) = (A · B) / (||A|| \* ||B||)**
> 
> **A · B: The dot product of vectors A and B.**
> 
> **||A|| and ||B||: The magnitude (Euclidean norm) of vectors A and B.**

Consider these sentence.

sentence 1: I am Iron Man

sentence 2: Iron can rust.

we will get vector matrix like this,

![](https://miro.medium.com/v2/resize:fit:875/1*QHpkH_dGR3lqyiD-UyOIog.jpeg)

Cosine similarity formula,

![](https://miro.medium.com/v2/resize:fit:875/1*QwnybRjYvuyWcvIb1XZCjQ.jpeg)

Applying this formula on top matrix,

![](https://miro.medium.com/v2/resize:fit:875/1*DNUkKBHfaa9_NnfwG23d8g.jpeg)

Giving us this on furthur calculation,

![](https://miro.medium.com/v2/resize:fit:875/1*m5_OOL4P1tU6PQzfA-JtGQ.jpeg)

The final similarity is

![](https://miro.medium.com/v2/resize:fit:875/1*rhO9y6D-KUQxi8wbej7eCw.jpeg)

The similarity is **_0.289_**, which seems accurate given the sentences.

## Use Cases and disadvantages

## Use Cases:

1.  **Document Similarity**: Cosine similarity is widely used in natural language processing to measure the similarity between documents. It’s applied in plagiarism detection, document clustering, and content recommendation systems.
2.  **Recommendation Systems**: In collaborative filtering-based recommendation systems, cosine similarity helps identify users or items with similar preferences. It’s used in movie, music, and product recommendations.
3.  **Text Classification**: In text classification tasks like spam detection, sentiment analysis, or topic modeling, cosine similarity can be used to compare the similarity between a document and predefined categories.
4.  **Information Retrieval**: Search engines use cosine similarity to match user queries with relevant documents by comparing the query vector to document vectors.
5.  **Clustering**: Cosine similarity aids in clustering similar data points together. For example, it’s used in grouping similar news articles or social media posts.

## Disadvantages:

1.  **Sensitivity to Document Length**: Cosine similarity doesn’t consider the length of documents. Longer documents may have lower cosine similarity scores even if they share substantial content.
2.  **Lack of Semantic Understanding**: Cosine similarity treats words or features as independent entities. It doesn’t capture the semantic meaning of words, making it less effective in understanding context.
3.  **Sparse Data Issues**: In high-dimensional spaces, where data is often sparse, cosine similarity can be less reliable. It might not accurately reflect the true similarity between data points.
4.  **Normalization Dependency**: Cosine similarity depends on vector normalization. Different normalization methods can yield different results, making comparisons sensitive to preprocessing choices.
5.  **No Negative Values**: Cosine similarity produces values between -1 and 1. It doesn’t handle negative associations well, which might be relevant in certain applications.
