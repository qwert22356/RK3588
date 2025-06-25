## Pull image
```bash
docker pull unclecode/crawl4ai:all-arm64
```

## Docker run 
```bash
docker run --rm -d \
  --network host \
  -e CRAWL4AI_API_TOKEN=12345 \
  --name crawl4ai \
  unclecode/crawl4ai:all-arm64
```
