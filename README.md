# Wikipedia Search Engine (Java + Redis)

A search engine that crawls Wikipedia pages, indexes their words in Redis, and answers Boolean search queries ranked by relevance.

Built as the final project for CSC 311 (Data Structures) at CSUDH, using the framework from *Think Data Structures* by Allen Downey.

## How it works
1. **Crawl:** `WikiCrawler` fetches Wikipedia pages with jsoup and queues the links found inside them.
2. **Index:** `JedisIndex` counts how often each word appears on each page and stores it in Redis as an inverted index (word → pages → counts).
3. **Search:** `WikiSearch` looks up terms and combines results with Boolean operations:
   - `and()`: pages containing both terms
   - `or()`: pages containing either term
   - `minus()`: pages containing the first term but not the second
4. **Rank:** results are sorted by relevance (total term frequency).

## Tech
Java · Redis (Jedis) · jsoup · JUnit · Ant

## Running it
1. Create a free Redis database (e.g., Redis Cloud).
2. Create `src/resources/redis_url.txt` containing your Redis URL. This file is ignored by Git and must never be committed.
3. Run `WikiSearch` to see sample search results.

## Sample output
See the screenshots in the `Outputs/` folder.
