# Description

Mock library for getUserMedia and related functions.

## Installation

`npm install @theopenweb/get-user-media-mock`

## Usage

The code below will automatically apply mocks to the following functions:

* navigator.getUserMedia
* navigator.mediaDevices.getUserMedia
* navigator.mediaDevices.enumerateDevices
* navigator.mediaDevices.getSupportedConstraints

```javascript
window.getUserMediaMock = new GetUserMediaMock();
getUserMediaMock.mock();
```

The code below will only apply mock stream if getUserMedia function(navigator.getUserMedia OR navigator.mediaDevices.getUserMedia) results in an error.

```javascript
window.getUserMediaMock = new GetUserMediaMock();
getUserMediaMock.fallbackMock();
```

For more advanced usage check [Functions].

## Functions

All functions below are on the main instance.
Type information uses TypeScript format. Types can be searched in the repository.

* setMediaUrl (url: string)
* setMockType (mockType: MockType)
* fallbackMock ()
* mock (options: MockOptions)
* restoreOldHandles ()
* getMockStreamFromConstraints
* getMockCanvasStream (constraints: MediaStreamConstraints)
* getMockMediaElementStream (constraints: MediaStreamConstraints)
* createStartedRandomCanvasDrawerInterval (canvas: HTMLCanvasElement)
* getConstraintBestValue (constraints: MediaStreamConstraints, type: MediaStreamTrackType, key: keyof MediaTrackConstraints)
* getMockDevices ()

## Support

Polyfills and transpiling(Babel, etc.) should be done outside of this library.

* [HTMLCanvasElement.captureStream](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
* [HTMLMediaElement.captureStream](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/captureStream)

## Dependencies

* [band.js - MIT](https://github.com/meenie/band.js)

## Test

```bash
npx http-server ./
# http://localhost:8080
```

## Test Media

Test Media are included for testing AND possibly mocking.
These media are not heavily depended on, so can be changed or removed if important.
If using build tools, the sizes should not be an issue. If there is an issue when building please contact.

* [Music - Public Domain Best_Of_-_Pick_Your_Player_-_09_Tequila_Moonrise](http://freemusicarchive.org/music/Tequila_Moonrise/Best_Of__Pick_Your_Player/Tequila_Moonrise)
* [Video - CC0 License](https://videos.pexels.com/videos/video-of-people-walking-855564)

