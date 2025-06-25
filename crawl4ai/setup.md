## Pull image
```bash
docker pull unclecode/crawl4ai:all-arm64
```

## Docker run 
```bash
docker run --rm -it \
-e CRAWL4AI_API_TOKEN=12345
-p 11235:11235 \
unclecode/crawl4ai:all-arm64
```
