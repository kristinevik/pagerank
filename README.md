# PageRank

My implementation of Google's PageRank algorithm. It crawls a folder of HTML pages, maps out who links to whom, and ranks the pages by importance.

The program computes PageRank in two different ways and prints both, so you can check they agree:

1. **Sampling (random surfer):** simulate someone clicking through 10,000 pages, usually following a link on the current page and sometimes jumping to a random page. A page's rank is the share of time the surfer spends on it.
2. **Iteration:** start every page at an equal rank and apply the PageRank formula over and over until no value changes by more than 0.001.

Both use a damping factor of 0.85. A page with no outgoing links is treated as linking to every page, so rank isn't lost in dead ends.

```
$ python pagerank.py corpus0
PageRank Results from Sampling (n = 10000)
  1.html: 0.2179
  2.html: 0.4290
  3.html: 0.2201
  4.html: 0.1330
PageRank Results from Iteration
  1.html: 0.2198
  2.html: 0.4294
  3.html: 0.2198
  4.html: 0.1311
```
*(Sampling numbers vary a little between runs.)*

## Run it

No dependencies, just Python 3:

```bash
python pagerank.py corpus0
python pagerank.py corpus1
python pagerank.py corpus2
```

Each `corpus*` folder is a small, self-contained "web" of linked HTML pages.

## Built with

Python (standard library only)
