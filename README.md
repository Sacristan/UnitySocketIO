## Usage:

```cs
    IEnumerator Start()
    {
        Debug.Log("Waiting for connection...");
        yield return SocketIOClient.AttemptConnection();
        Debug.Log("Connected!");

        SocketIOClient.On("authorised", OnAuthorised);
        SocketIOClient.On("unity_client_connected", OnClientConnected);
        SocketIOClient.On("unity_client_disconnected", OnClientDisconnected);
    }
    private void OnAuthorised(SocketIOEvent obj)
    {
        Debug.Log("Client authorized: " + obj.data);
    }

    private void OnClientConnected(SocketIOEvent obj)
    {
        Debug.Log("Client connected: " + obj.data);
    }

    private void OnClientDisconnected(SocketIOEvent obj)
    {
        Debug.Log("Client disconnected: " + obj.data);
    }
```

For original author - see readme. I would be glad to fork this repo :)
