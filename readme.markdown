This fork is a quick and dirty edit of Joel Hooks' original signals-extension-CommandSignal that allows the signal arguments to be passed into the execute() method as parameters instead of being injected into the command.  This allows multiple parameters of the same type

## Usage

To make use of this functionality your command needs to extend `SignalArgumentsCommand` and implement an `execute()` method:

```as3
// The command class
public class MyCommand extends SignalArgumentsCommand {
  
  [Inject]
  public var myModel:MyModel;

  public function execute(param1:String, param2:String, param3:Boolean) {
  }

}

// The signal
var executeMyCommandSignal:Signal = new Signal(String, String, Boolean);

```

Note that if the command doesn't extend SignalArgumentsCommand the parameters will get injected as usual.

Many thanks to Michael Cann who came up with the idea in [this thread](http://groups.google.com/group/robotlegs/browse_thread/thread/673b988e07855867/7520804fad072805)

## SignalCommandMap

The SignalCommandMap is an extension for the Robotlegs-AS3 micro-architecture that makes use of AS3-Signals to trigger commands.

[Requires Robotlegs 1.1](http://github.com/robotlegs/robotlegs-framework)

[Here is an example and more details](http://joelhooks.com/2010/02/14/robotlegs-as3-signals-and-the-signalcommandmap-example/)