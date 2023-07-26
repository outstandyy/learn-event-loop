# learn-event-loop

JS Event Loop realization

```
while(true) {
  // get first normal task from some queue
  task = eventLoop.nextTask(); 

  if (task) {
      // execute that single task
      task.execute(); 
  }
  
  // execute all microtasks until none are left
  eventLoop.executeMicrotasks(); 
  
  // browser-specific: render if needed
  if (eventLoop.needsRendering()) {
      eventLoop.render();
  }
}
```
