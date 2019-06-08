---
layout: default
---

Text can be **bold**, _italic_, ~~strikethrough~~ or `keyword`.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```
<?php

namespace RangInfo;

use pocketmine\Server;
use pocketmine\Player;
use pocketmine\utils\TextFormat as SG;
use pocketmine\utils\Config;
use pocketmine\event\Listener;
use pocketmine\plugin\PluginBase;

use pocketmine\command\{Command,CommandSender};

class Main extends PluginBase implements Listener{
	
	public $prefix = '§8[§4Rang§aInfo§8] §7§l»§r';
	
	public function onLoad(){
		$this->getLogger()->info($this->prefix . ' §a§lLade §4§lRangInfo');
		$this->getLogger()->info($this->prefix . ' §a§lMade by §4§lzCuzImMarcel!');
	}
	
	public function onEnable(){
		$this->getLogger()->info($this->prefix . ' §a§lGeladen!');
		$this->getLogger()->info($this->prefix . ' §a§lDas Plugin wurde von');
		$this->getLogger()->info($this->prefix . ' §4§lzCuzImMarcel §a§lGemacht!');
		@mkdir($this->getDataFolder());
		$config = new Config($this->getDataFolder()."ranks.yml", Config::YAML);
		
	}
	
	public function onCommand(CommandSender $player, Command $cmd, string $label, array $args):bool{
		
		switch($cmd->getName()){
			case "premium":
			if($player instanceof Player){
				$player->sendMessage(SG::GOLD . "Premium" . SG::GRAY . " hat folgende" . SG::RED . " Rechte " . SG::RESET);
				$player->sendMessage(SG::GRAY . "Du kannst Fliegen mit " . SG::YELLOW . "/" . SG::GREEN . "fly" . SG::GRAY . " !");
				$player->sendMessage(SG::GRAY . "Du kannst in den " . SG::RED . "GodModus" . SG::GRAY . " mit " . SG::YELLOW . "/" . SG::GREEN . "god" . SG::GRAY . " gehen!");
				$player->sendMessage(SG::GRAY . "Du kannst deinen " . SG::RED . "Rand" . SG::GRAY . "Ändern mit " . SG::YELLOW . "/" . SG::GREEN . "p rand");
			}
			break;
			case "nutzer":
			if($player instanceof Player){
				$player->sendMessage(SG::GRAY . "Der Nutzer" . SG::GRAY . " ist der Standart Rang!");
				$player->sendMessage(SG::GRAY . "Wir bedanken uns dafür das du uns damit " . SG::GREEN . "Unterstützt" . SG::GRAY . "!");
			}
			break;
			case "titan":
			if($player instanceof Player){
				$player->addTitle(SG::BLUE . "Titan");
				$player->sendMessage(SG::GRAY . "Der" . SG::BLUE . " Titan " . SG::GRAY . "hat folgende" . SG::RED . " Rechte " . SG::RESET);
				$player->sendMessage(SG::GRAY . "Die von " . SG::GOLD . " Premium" . SG::RESET);
				$player->sendMessage(SG::GRAY . "Du kannst deinen Rand ändern mit " . SG::YELLOW . "/" . SG::GREEN . "p rand");
				$player->sendMessage(SG::GRAY . "Danke für die " . SG::GREEN . "Unterstützung" . SG::GRAY . "!");
			}
			break;
			case "platin":
			if($player instanceof Player){
				$player->addTitle(SG::BLUE . "Platin");
				$player->sendMessage(SG::GRAY . "Der " . SG::BLUE . "Platin" . SG::GRAY . "hat folgende " . SG::RED . "Rechte");
				$player->sendMessage(SG::GRAY . "Du hast die " . SG::RED . "Rechte " . SG::GRAY . "von " . SG::GOLD . "Premium " . SG::GRAY . "&" . SG::BLUE . " Titan " . SG::GRAY . "&" . SG::BLUE . " Platin");
				$player->sendMessage(SG::GRAY . "Du kannst dich Nicken mit " . SG::YELLOW . "/" . SG::GREEN . "nick" . SG::GRAY . " [Name]");
				$player->sendMessage(SG::GRAY . "Du kannst dich Heilen mit " . SG::YELLOW . "/" . SG::GREEN . "heal");
				$player->sendMessage(SG::GRAY . "Du kannst " . SG::RED . "Slapper " . SG::GRAY . "Erstellen!");
			}
			break;
			case "griefer":
			if($player instanceof Player){
				$player->adTitle(SG::GREEN . "Griefer");
				$player->sendMessage(SG::GRAY . "Der " . SG::GREEN . "Griefer " . SG::GRAY . "Rang hat folgende" . SG::RED . " Rechte");
				$player->sendMessage(SG::GRAY . "Du hast die " . SG::RED . "Rechte " . SG::GRAY . "von " . SG::BLUE . "Platin & Titan " . SG::GRAY . "&" . SG::GOLD . " Premium" . SG::GRAY . " Ranges");
			}
			break;
			case "supreme":
			if($player instanceof Player){
				$player->sendMessage(SG::GRAY . "Der " . SG::RED . "Supreme " . SG::GRAY . "hat folgende " . SG::RED . "Rechte");
				$player->sendMessage(SG::GRAY . "von den Rängen darunter!");
			}
			break;
			case "rangliste":
			if($player instanceof Player){
				$player->sendMessage(SG::GRAY . "");
				$player->sendMessage(SG::GRAY . "Es gibt folgende §cRänge");
				$player->sendMessage(SG::GRAY . "");
				$player->sendMessage(SG::GRAY . "§6Premium§8, §dSupreme§8, §2Griefer§8, §bPlatin§8, §9Titan§r");
				$player->sendMessage(SG::GRAY . "");
				$player->sendMessage(SG::GRAY . "§7Diese §cRänge §7gibt es !");
			}
			break;
			case "aboutranks":
			if($player instanceof Player){
				$player->sendMessage(SG::GRAY . "[" . SG::DARK_RED . "RangInfo" . SG::GRAY . "]" . SG::GRAY . " Das Plugin wurde für " . SG::BOLD . SG::DARK_RED . "Sky" . SG::YELLOW . "Games" . SG::AQUA . "PE" . SG::GRAY . "gemacht!" . SG::RESET);
				$player->sendMessage(SG::GRAY . " ");
				$player->sendMessage(SG::GRAY . "[" . SG::DARK_RED . "RangInfo" . SG::GRAY . "]");
				$player->sendMessage(SG::GRAY . "Das wurde von " . SG::BOLD . SG::GREEN . "zCuzImMarcel" . SG::RESET);
			}
			break;
		}
		return true;
	}
	
	public function onDisable(){
		$this->getLogger()->info($this->prefix . '§4§lPlugn wurde deaktiviert!');
		$this->getLogger()->info($this->prefix . '§a§lMade by §4§lzCuzImMarcel!');
	}
}
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
