ℹ️**This is written as an answer to an FAQ and is meant for portfolio purposes only.**
# Use Algolia or ElasticSearch index ranking
An optimal search experience predicts a user's intent and leverages that intelligence to populate the most relevant results. For consumer-grade search, to connect people with products, search indexing (and ranking) should support speed, user relevance tuning, and performer optimization.
## ElasticSearch ranking formula 
ElasticSearch is an open-source search and analytics engine that can be configured to collect and analyze log data, perform simple searches on a website, or implement data visualization tools. Users are expected to maintain, host, and regularly upgrade the software to prevent inaccurate queries or performance delays. This maintenance can impact performance features and as expectations for quality user experiences scale, it gets harder to secure accurate queries. 
### Elastic ranking tf-idf approach 
ElasticSearch uses the tf-idf (term frequency-inverse document frequency) approach to measure the frequency of query words and match documents with a score. The score determines the relevance of the queries to populate results. Though ideal for indexing large records, documents, and webpages, there is no opportunity to configure queries to account for human errors including misspelled words, or incorrect spacing. 
For example, if a search query is for "Bookworm" but the user entered "Bokwrm", the results from sorting the query may be inaccurate and irrelevant. The query would then need to be configured to include possible entries.
## Algolia ranking formula 
Algolia's ranking is based on more than the count of queried words and the goal is to match prefixes, not words. For example, if the user is searching for "Harry Potter", but enters the search query "Har Pottr", the possible matches may be as follows: 
* Harry Potter 
* Harry Pottur 
* Harry Potterl 
Algolia’s default ability to optimize results offers a lightweight solution to configure possible entries. 
### Algolia ranking  tie-breaking approach 
Algolia's tie-breaking approach works iteratively, using custom ranking attributes to select results against strict criteria such as follows: 
* Typo: users can make typing mistakes with 0, 1, or 2 mistakes per word, and still find the right answer. By default, the correct spelling is ranked highest. 
* Geo: queries can be ranked by distance, or limited to a specified geographical location. 
* Words: some words can be configured as optional to yield the same relevant results. 
* Filters: queries can have filters to rank records based on a filtering score.

The software uses these criteria to match records and score results. In the case of a tie, the preceding criterion provides a ranking technique to select the optimal and most relevant result. This assures that the user can find the most relevant results, as their input is sifted through multiple criteria. 
## Algolia or ElasticSearch
Search ranking is an iterative process that involves matching, sorting, and analyzing data, to produce the most relevant outcome. Quality search experience relies on latency, performance, and producing relevant results. The decision on when to use either ElasticSearch or Algolia for consumer-grade search indexing needs depends on the scope of the expectations for an optimal search experience.
