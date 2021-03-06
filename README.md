# Signals
Small Unity library that allows decoupled scripts to communicate events to each other easily.

#### Benefits
* Organise your games signals using filesystem directory structure
* Reduces FindObjectsOfType and GetComponent and other reference hunting code.
* Signals can be triggered from the inspector for testing purposes
* Scene independant ( define once, use in multiple scenes )

## Installation
Download and install latest release [unitypackage](https://github.com/paulhayes/Signals/releases/download/v0.1.1/Signals.unitypackage)

## Usage
Examples can be found in ```Assets/Signals/Examples```


Create Signals from main menu ***Assets->Create->Signal***. 


#### Sender code
```
public Signal signal;

void SomeMethod(){
  signal.Trigger();
}
```

#### Listener code
```
public Signal signal;

void OnEnable(){
  signal.Attach(OnSignal);
}

void OnDisable(){
  signal.Detach(OnSignal);
}

void OnSignal(object obj){
  //signal recieved
}
```

