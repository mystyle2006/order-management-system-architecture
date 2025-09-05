# Background
At Gomi Corporation, as a commerce platform, there was a requirement to integrate and manage orders from Southeast Asian shopping platforms such as Shopee and Lazada. Since each shopping platform offered webhooks, we leveraged them to implement the order management system.

We selected an asynchronous architecture for the following reasons:
- During major events like promotions and big sales, the platform experiences a surge in order volume.
- Since most external shopping platform webhooks had short timeouts, we responded quickly and processed the data asynchronously within our system.
- Processing orders immediately would complicate retries and fault recovery.

# Details
