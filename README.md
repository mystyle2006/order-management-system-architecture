# Background
At Gomi Corporation, as a commerce platform, there was a requirement to integrate and manage orders from Southeast Asian shopping platforms such as Shopee and Lazada. Since each shopping platform offered webhooks, we leveraged them to implement the order management system.

We selected an asynchronous architecture for the following reasons:
- During major events like promotions and big sales, the platform experiences a surge in order volume.
- Since most external shopping platform webhooks had short timeouts, we responded quickly and processed the data asynchronously within our system.
- Processing orders immediately would complicate retries and fault recovery.

# Details

![OMS Bluescreen](./OMS.drawio.png)

Northeast Shopping Platform: Based on webhooks provided by Southeast Asian shopping platforms, order events are delivered to our internal servers.
API Gateawy: To prevent Lambda overload during webhook event spikes, we implemented traffic control to regulate the delivery rate. Additionally, by attaching ACM certificates, we automated HTTPS and TLS management, maximizing production efficiency.
