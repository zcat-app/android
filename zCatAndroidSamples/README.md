# zCatAndroidSamples

Examples of how I used [TorAndroid library](https://github.com/guardianproject/tor-android) in my Android Apps. It is far from optimal and
far from ideal, I build it when I learned on the fly. Feel free to do whatever you want with that. If it helps anyone good, if it 
set example how not to use it, also good. Cheers.

## What you find here
These examples show:
- Initialization of Tor proxy
- Rest Calls through Tor
- Websites fetching in Webview with Tor
- Websockets with Tor proxy
- Fetching Images with Glide through Tor

## Components
- ### TorActivity
    Simple wrapper for activity that tries to start Tor connection. See [TorActivity](app/src/main/java/examples/zcat/zcatandroidsamples/ui/tor/TorActivity.java).

- ### TorActivityWithRest
    Extension of TorActivity that provides callbacks for REST calls (if any needed),
that are performed only after the Tor connection is established. [TorActivityWithRest](app/src/main/java/examples/zcat/zcatandroidsamples/ui/tor/TorActivityWithRest.java).

- ### Glide App Module
    Custom Glide Module ([TorActivityWithRest](app/src/main/java/examples/zcat/zcatandroidsamples/glide/OkHttpLibraryGlideModule.java)) for the 
[Glide library](https://github.com/bumptech/glide) with custom loader that can use HTTP client with Tor proxy to fetch images.

- ### WebsocketActivity
    TorActivityWithRest extension that initializes WebSocket Clients after the Tor connection is established. See [WebsocketActivity](app/src/main/java/examples/zcat/zcatandroidsamples/ui/websocket/WebsocketActivity.java).

- ### WebActivity
    TorActivityWithRest extension that intercepts requests and redirect them through the Tor network. See
[WebActivity](app/src/main/java/examples/zcat/zcatandroidsamples/ui/webview/WebActivity.java).

## App
The app is simple showcase with of possible ways how to (or not to) implement Tor-Android library into your project. As 
example it fetches data from Zcash forum to see latest posts. It uses websocket connection to get live ticker (prices) 
data from exchange, or it tries to fetch image or website. You should be able to turn on/off usage of the Tor proxy. 