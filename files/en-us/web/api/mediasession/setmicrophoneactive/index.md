---
title: "MediaSession: setMicrophoneActive() method"
short-title: setMicrophoneActive()
slug: Web/API/MediaSession/setMicrophoneActive
page-type: web-api-instance-method
browser-compat: api.MediaSession.setMicrophoneActive
---

{{APIRef("Media Session API")}}

The **`setMicrophoneActive()`** method of the {{domxref("MediaSession")}} interface is used to indicate to the user agent whether the user's microphone is considered to be currently muted.

Call this method on the `navigator` object's
{{domxref("navigator.mediaSession", "mediaSession")}} object.

Note that the status of the microphone is not tracked in the {{domxref("MediaSession")}} itself, but must be tracked separately.

## Syntax

```js-nolint
setMicrophoneActive(active)
```

### Parameters

- `active`
  - : A boolean indicating whether the microphone is considered muted or not.

### Return value

None ({{jsxref("undefined")}}).

## Examples

Below is an example of updating the microphone mute state of the current
{{domxref('MediaSession')}}, as well as listening to requests to change the mute status with {{domxref("MediaSession.setActionHandler", "setActionHandler()")}}.

```js
let microphoneActive = false;

navigator.mediaSession.setMicrophoneActive(microphoneActive);

navigator.mediaSession.setActionHandler("togglemicrophone", () => {
  microphoneActive = !microphoneActive;
  navigator.mediaSession.setMicrophoneActive(microphoneActive);
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
