# tinyurl
A resolution of tinyurl

## Requirement
This is a problem from leetcode, you can find the original problem [here](https://leetcode.com/problems/design-tinyurl/description/)
The detailed requirement is like this:
1. Convert any url to short url like: http://tinyurl.com/4e9iAk
2. The last segment is the id, which has 6 characters, and each character is from '0-9a-zA-Z'
3. No two different urls have the same short url

## The resolution
1. Total count of possible short url is 62^6 - 1 = 56800235583. We can name is MAX_ID.
2. For a given url, assign it a free id (which has not been used) with in MAX_ID.
3. Store the <id, url> pair to database like mysql or redis, or even a txt file.
4. Convert the id of number to id of short url, 10 based digit to 62 based digit.


## Answers to questions in original problem
1. How many unique identifiers possible? Will you run out of unique URLs?
> Possible of 56800235583 unique identifiers. Yeah, it will run out of unique URLSs.
2. Should the identifier be increment or not? Which is easier to design? Pros and cons?
> It could be either increment or not. Increment way is easier to design. 
3. Mapping an identifier to an URL and its reversal - Does this problem ring a bell to you?
4. How do you store the URLs? Does a simple flat file database work?
> YES
5. What is the bottleneck of the system? Is it read-heavy or write-heavy?
6. Estimate the maximum number of URLs a single machine can store.
7. Estimate the maximum number of queries per second (QPS) for decoding a shortened URL in a single machine.
8. How would you scale the service? For example, a viral link which is shared in social media could result in a peak QPS at a moment's notice.
9. How could you handle redundancy? i,e, if a server is down, how could you ensure the service is still operational?
10. Keep URLs forever or prune, pros/cons? How we do pruning? (Contributed by @alex_svetkin)
11. What API would you provide to a third-party developer? (Contributed by @alex_svetkin)
12. If you can enable caching, what would you cache and what's the expiry time? (Contributed by @Humandroid)