
# Common layer across most applications

## Authentication

## Authorization

## Transport protocols

### HTTP/HTTPS

### HLS/DASH:
HLS(HTTP Live Streaming) is an HTTP-based adaptive bitrate streaming protocol.
Similar to MPEG-DASH or just DASH(**Dynamic Adaptive Streaming over HTTP**). However, DASH required 

# Domain Specific knowledge

## Streaming/Live Streaming

### Segmentation

### Transcoding

# Practicals

## Design a rate limiter
Introduce as a middleware. Helps in keeping a state across deployment regions.
In a possible scenario, we can also queue the pending messages. This can work in conjunction with some webhook for future communications.

For distributed, use a centralized data store such as redis. Can perhaps use WATCH with redis transactions to acquire a lock to avoid race conditions.

### Algorithms:

#### Token Bucket
Easiest, recommended. Tokens are generated at some rate. Every request consumes one token. Extra tokens overflow

#### Leaky Bucket 
Fixed length queue of requests. If queue full. Drop requests. Consume requests at a specific interval. Not advised for customer facing.

#### Fixed Window counter
Window is fixed and requests are counted against it. Can lead to system abuse as the burst traffic is sometimes acceptable beyond limits.

#### Sliding Window log
Instead of a fixed window, we have a sliding window. Consumes lots of memory as it keeps a track of all the timestamps of the requests.

#### Sliding Window Counter
Hybrid approach. 


