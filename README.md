# WFT-Tags-Example
Example of how to add your own tags to WFT

## Instructions:
1. Create an EventListener 
2. Create an listen for the event TagReplaceEvent
3. Get the text using the function `getText()`
4. Replace the required string with `str_replace()`, built into php
5. Set the text with the `setText($text)`

## Example:
```php

// Import the event class
use WolfDen133\WFT\Event\TagReplaceEvent;

use pocketmine\event\Listener;


// Create the event listener class
class EventListener extends Listener {


// Listen for the TagReplaceEvent driven by the plugin
  public function onTagReplaceEvent (TagReplaceEvent $event) : void
  {
    // Get the text from the event
    $text = $event->getText();
    
    // Replace the tags you need
    $replace = str_replace(["{tag1}", "{tag2}"], ["Value 1", "Value 2"], $text);
    
    // And replace the text
    $event->setText($replace);
  }
  
}
```

Thats it, easy!
