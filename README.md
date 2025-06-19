# n8n Extended: Featuring Puppeteer and Curl
https://hub.docker.com/r/thinhpxp/n8nplus
This Docker image is based on the official `n8nio/n8n` image and extends its capabilities by pre-installing two powerful command-line tools: **Puppeteer** and **Curl**.

This custom image provides a more versatile environment for advanced web automation, data scraping, and command-line networking tasks directly within your n8n workflows.

## Why Use This Image?

The standard n8n image is excellent for most integrations, but some advanced scenarios require direct browser automation or specific command-line utilities. This image is designed for users who need:

*   **Web Scraping & Automation:** Utilize **Puppeteer** to control a headless Chrome or Chromium browser. This is essential for interacting with websites that heavily rely on JavaScript, single-page applications (SPAs), filling out forms, taking screenshots, or performing complex navigation steps that the standard HTTP Request node cannot handle. Access Puppeteer capabilities via n8n's 'Execute Command' or 'Code' nodes.
*   **Advanced HTTP Requests:** While n8n has a dedicated HTTP Request node, having **Curl** available via the 'Execute Command' node offers flexibility for specific use cases, testing complex API interactions, or leveraging Curl's extensive options directly.
*   **Unified Environment:** Run your n8n workflows alongside browser automation and command-line tools within a single, contained Docker environment, simplifying setup and dependencies.

## Included Tools

This image includes:

*   The standard n8n installation (based on the specific `n8nio/n8n` tag this image was built from).
*   **Puppeteer** and its required browser dependencies.
*   **Curl**.

## How to Use

To get started with this image, pull it from Docker Hub:

```bash
docker pull thinhpxp/n8nplus:v1.0
```
Then, run it just like you would a standard n8n container, ensuring you map ports and volumes as needed for persistent data:
```bash
docker run -it --rm \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  thinhpxp/n8nplus:v1.0
```
Access your n8n instance via your web browser at http://localhost:5678 (or the port you configured).
Within your n8n workflows, you can now use the Execute Command node to run puppeteer scripts or curl commands, leveraging the pre-installed tools.
Based On
This image is based on the official n8nio/n8n Docker image.
