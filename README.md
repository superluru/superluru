# superluru
private PlutoconManager plutoconManager;

// Initialization
plutoconManager = new PlutoconManager(context);
plutoconManager.connectService(new PlutoconManager.OnReadyServiceListener() {
	@Override
	public void onReady() {
		//do something
	}
});


// Start monitoring foreground with listener
plutoconManager.startMonitoring(PlutoconManager.MONITORING_FOREGROUND, new PlutoconManager.OnMonitoringPlutoconListener() {
	@Override
	public void onPlutoconDiscovered(Plutocon plutocon, List<Plutocon> plutocons) {
		//do something	
	}
});

// Start monitoring background
plutoconManager.startMonitoring(PlutoconManager.MONITORING_BACKGROUND, new PlutoconManager.OnMonitoringPlutoconListener() {
	@Override
	public void onPlutoconDiscovered(Plutocon plutocon, List<Plutocon> plutocons) {
		//do something	
	}
});

// Stop Monitoring
plutoconManager.stopMonitoring();

// Disconnect from manager service.
plutoconManager.close();
```

### Quick start for connecting sensor
````java
// Initialization
PlutoconConnection plutoconConnection = new PlutoconConnection(context);

// Connect to plutocon
plutoconConnection.connect(new PlutoconConnection.OnConnectionStateChangeCallback() {
	@Override
	public void onConnectionStateDisconnected() {
		//do something		
	}

	@Override
	public void onConnectionStateConnected() {
		//do something		
	}
});

// Read plutocon property
plutoconConnection.getBatteryVoltage();
plutoconConnection.getBroadcastingPower();
plutoconConnection.getAdvertisingInterval();

plutoconConnection.getUuid();
plutoconConnection.getLatitude();
plutoconConnection.getLongitude();

plutoconConnection.getSoftwareVersion();
plutoconConnection.getHardwareVersion();
plutoconConnection.getManufactureName();
plutoconConnection.getModelNumber();

// Disconnect from plutocon
plutoconConnection.disconnect();
