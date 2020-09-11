# Android-Event-Listener
Use the Android Event Listener to run a handler when users put the app in the background – for example, locking the screen, changing apps or going to the home screen. You can also run a handler when users get back into your app after leaving it! 

This library, once started, will run certain handlers when your app goes in and out of the background. To start it, run "StartListener" in your card/stack, and when you're closing it, run "StopListener" to stop it. When your app goes into the background, the handler "StackPaused" will be executed, and when your app comes back the handler "StackResumed" will run. Since this all needs to be on mobile, it's recommended to check the environment before starting or stopping the listener, otherwise you'll get an error! Hopefully this all works properly, so enjoy! Also make sure to include the Android Event Listener in the inclusions of the app

Example:
```
on openStack
   if the environment is "mobile" then 
      StartListener
   end if
end openStack

on closeStack
   if the environment is "mobile" then 
      StopListener
   end if
end closeStack

on StackPaused
   -- do action to pause the stack
end StackPaused

on StackResumed
   -- do action to unpause the stack
end StackResumed
```

Note: I'm still quite new to this, so at the moment if you don't have BOTH pause AND resume handlers available, it throws an error in the IDE. Not sure what happens if you're running it without one of the handlers in Android though. Just to be safe though, I recommend having both handlers, even if one is empty and unused :)

Note: When the app is paused, everything will run, but sometimes when you're looking at the list of opened apps, the screen won't show that anything has updated, even though in the background it will be suspended. Thus, if you have anything in your app that updates the look of your app when paused, it may not look like that's happened, when in reality it has
