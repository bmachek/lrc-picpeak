# lrc-picpeak

A Lightroom Classic plugin that uploads photos to a self-hosted [PicPeak](https://github.com/the-luap/picpeak) gallery server.

## Features

- **Export workflow** — upload selected photos directly to a PicPeak event during export
- **Publish workflow** — maintain Lightroom publish collections synced to PicPeak events; re-uploads are skipped for already-published photos
- **Event creation** — create new events with full details (name, type, date, customer info, password protection, expiry, guest feedback, color theme) without leaving Lightroom
- **Plugin metadata** — `picpeakPhotoId` and `picpeakEventId` written back to each photo after upload

## Requirements

- Adobe Lightroom Classic
- A running PicPeak server (v1 API)
- A PicPeak API token with `write` + `admin` scopes

## Installation

1. Download or clone this repository.
2. In Lightroom Classic, open **File → Plug-in Manager**.
3. Click **Add** and point it at the `picpeak-plugin.lrplugin/` directory.
4. Click **Done**.

The plugin appears in the Export dialog and in the Publish Services panel.

## Setup

1. In the Export or Publish dialog, find the **PicPeak Server** section.
2. Enter your server URL (e.g. `https://picpeak.example.com`) and API token.
3. Click **Test Connection** to verify.

Credentials are stored in Lightroom preferences and reused across sessions.

## Usage

### Export

1. Select photos in Lightroom, then go to **File → Export**.
2. Choose **PicPeak Exporter** as the export destination.
3. Under **PicPeak Gallery Event**, pick one of:
   - **Choose on export** — a picker appears at export time
   - **Existing event** — select from a dropdown of your events
   - **Create new event** — fill in event details inline
4. Configure the rest of your export settings (format, size, etc.) and click **Export**.

### Publish

1. In the **Publish Services** panel, click **Set Up** next to PicPeak Publisher (or right-click to add a collection).
2. When creating a collection, choose to create a new PicPeak event or bind to an existing one.
3. Drag photos into the collection and click **Publish**.

> **Note:** The PicPeak v1 API does not support deleting or renaming events or photos. The plugin will warn you if you attempt these operations and mark the photos as handled in Lightroom without modifying the server.

## Supported Event Types

`wedding` · `birthday` · `corporate` · `family` · `other`

## License

MIT
