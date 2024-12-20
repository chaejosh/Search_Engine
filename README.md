# Search_Engine
## Utilizing Service-Oriented Architecture to scale dynamic pages and web search
### demos from a local host run

![image](https://github.com/user-attachments/assets/5eed8f2c-7bb1-4233-bacf-c69937fed8d7)
Graphical user interface implemented to accept a query and the weight as inputs to return the ranked list of the top 10 relevant documents

The slider allows the user to specify a PageRank weight

https://github.com/user-attachments/assets/7420c94b-c739-45cd-ada8-5ebde1e82efc

Utilized retrieval concepts such as tf-idf (text analysis) and PageRank (link analysis), along with a pipeline of MapReduce programs for parallel data processing

Implemented three servers:
- Inverted index server: pipeline of MapReduce programs that takes in a subset of Wikipedia documents crawled from Michigan/tech-related seed pages. Outputs inverted index of inverse document frequency (idf), term frequency (tf), and the normalization factor, all segmented by the document-id
- Index server: REST API app that returns search results in JSON format. Run one index server for each inverted index segment
- Search server: server-side dynamic pages app that returns search results in HTML format. Makes calls to each Index server segment in parallel threads and combines the results

UI utilized HTMX and CSS

Backend was implemented with Python and Flask for routing and requests
