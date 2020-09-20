# Device registry service

## Usage

All responses will have the following form

```json
{
  "data": "Mixed type holding content of response"
}
```


Details of the 'data' field

### List all devices

`GET /devices`

**Response**

- '200 OK' on success

```json
{
  "identifier": "huawei52",
  "name": "téléphone issam",
  "device_type": "phone",
  "controller_gateway": "192.1.68.0.2"
}
```

### Register new device

`POST /devices`

**Arguments**

- `"identifier":string` a globally unique identifier for device
- `"name":string` a friendly name for device
- `"device_type":string` the type of the device
- `"controller_gateway":string` the IP adress of the device's controller

**Responses**

- '201 Created' on success

```json
{
  "identifier": "huawei52",
  "name": "téléphone issam",
  "device_type": "phone",
  "controller_gateway": "192.168.0.8"
}
```

### Delete a device

`DELETE /device/<identifier>`

**Responses**

- '404 not found' if device does not exist
- '204 Success' if deletion completed successfully
