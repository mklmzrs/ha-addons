# smart-home-yvr

Run the NestJS API image as a Home Assistant add-on.

## What this add-on runs

- Image: `ghcr.io/mklmzrs/smart-home-yvr:latest`
- Internal service port: `3000`
- Health endpoint: `GET /health`
- Test endpoint: `GET /api/v1/test`
- Home Assistant webhook endpoint: `POST /api/v1/webhooks/homeassistant`
- Due task processing: internal cron every 5 minutes
- Swagger UI: `/api/docs`

## Installation

1. Add this repository to Home Assistant:
   - **Settings -> Add-ons -> Add-on Store -> 3-dot menu -> Repositories**
   - Add: `https://github.com/mklmzrs/smart-home-yvr`
2. Open the add-on **smart-home-yvr**.
3. Click **Install**.
4. Configure the add-on (see configuration below).
5. Click **Start**.

## Configuration

Example add-on configuration:

```yaml
api_key: "change-me"
az_storage_account_name: "yourstorageaccount"
az_storage_account_key: "..."
reolink_base_url: "http://10.0.0.20/cgi-bin/api.cgi"
reolink_user: "admin"
reolink_password: "..."
reolink_blob_container: "reolink"
smartthings_token: "..."
twilio_account_id: "AC..."
twilio_api_key: "..."
twilio_sms_from: "+17784027879"
twilio_whatsapp_from: "whatsapp:+17784027879"
owner_phone_number: "+12505550123"
smartthings_lock_device_id: "..."
smartthings_climate_device_id: "..."
```

## Troubleshooting

### Add-on does not start

- Check add-on logs from Home Assistant UI.
- Confirm your image is reachable in GHCR:
  - `ghcr.io/mklmzrs/smart-home-yvr:latest`
- Verify architecture support (`aarch64`, `amd64`, `armv7`) is available for the image manifest.

### API unreachable on port 3000

- Ensure add-on is running.
- Confirm port mapping `3000/tcp: 3000` is not conflicting with another add-on.

### Authentication failures

- Verify `api_key` value in add-on configuration.
- Restart add-on after changing configuration.
