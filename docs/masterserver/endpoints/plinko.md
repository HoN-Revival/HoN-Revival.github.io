# Plinko

## Background

### Odds

There does not appear to be an official posting of the probabilities (I believe this was once published
on the old forums, but is long gone). However my boy `stimd` did his own experiment over 153 rolls to
determine the following probabilities:

- 90 (57.69%) were 30 tickets
- 21 (13.46%) were 60 tickets
- 25 (16.03%) were Silver Chests
- 16 (10.26%) were URSA Chests
- 3 (1.92%) were Gold Chests
- 1 (0.64%) was a Diamond Chest

[source](https://www.reddit.com/r/HeroesofNewerth/comments/2qaz3l/plinko_statistics_revealed/)

Given these metrics, my proposed probabilities (which are a bit more generous) are:

  - Diamond Chest (2%)
  - Gold Chest (4%)
  - Silver Chest (20%)
  - Bronze Chest (25%)
  - 60-tickets (15%)
  - 30-tickets (34%)

This yields a 51% chance of hitting 'some chest' and 49% of hitting tickets. And, for each
category of chest, it has a higher individual probability than the sample data set.

### Prizes

No clue how accurate this is, but according to the fandom [wiki](https://hon.fandom.com/wiki/HoN_Plinko)
the prizes in each chest roughly correspond to:

- Bronze Chest: Win an Alt Avatar priced between 99 and 351 Gold.
- Silver Chest: Win an Alt Avatar priced 352 Gold or more.
- Gold Chest: Win a Limited Edition or Holiday Edition Alt Avatar.
- Diamond Chest: Win a selection of Plinko Only, Early Access, Gold Collection, Ultimate, Item, Debut Edition, 7 Deadly Sins, or 7 Heavenly Virtues Alt Avatar or limited edition Announcers.

If the player owns all the Alt Avatars within the prize offerings, they receive Tickets instead, as follows:

- Bronze / Special: 80
- Silver: 100
- Gold: 225
- Diamond: 350

#### Special Prizes?

For certain periods of time, the Bronze Chest is replaced with a different chest, offering specific sets of Alt Avatars as prizes.
A percentage of profits generated from Plinko went towards major HoN tournaments.

- Paragon Chest: Win a Paragon Alt Avatar or an upgrade to a Paragon Alt Avatar. Replaced the Bronze Chest until May 17, 2016. Proceeds went towards HoN Tour cycle prize pool.
- DreamHack Chest: Win an A.R.M.S. Alt Avatar. Replaced the Bronze Chest until June 16, 2015. Proceeds went towards Dreamhack Summer 2015.
- URSA Corps Chest: Win an eSports Alt Avatar. Replaced the Bronze Chest until March 10, 2015. Proceeds went towards the HoNTour Grand Finals prize pool.

## /master/casino/

Called when opening Plinko. this response returns the 

### Request

```
POST /master/casino/ HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 39
Content-Type: application/x-www-form-urlencoded

cookie=8594ebfe66007296fd36e92319d67be6
```

### Reponse

```
a:9:{s:11:"status_code";i:1;s:5:"tiers";a:6:{i:0;s:1:"5";i:1;s:1:"3";i:2;s:1:"4";i:3;s:1:"1";i:4;s:1:"6";i:5;s:1:"2";}s:11:"ticket_cost";s:2:"66";s:9:"gold_cost";s:2:"54";s:9:"user_gold";s:4:"4252";s:6:"silver";s:5:"22563";s:12:"user_tickets";s:4:"1085";s:18:"amount_of_products";s:19:"0,772,659,233,0,263";s:16:"last_update_time";s:65:"1502806719,1639282922,1639282923,1639282922,1502424000,1639282922";}
```

```
Array
(
    [status_code] => 1
    [tiers] => Array
        (
            [0] => 5   // 60-tickets
            [1] => 3   // Silver Chest
            [2] => 4   // Bronze Chest
            [3] => 1   // Diamond Chest
            [4] => 6   // 30-tickets
            [5] => 2   // Gold Chest
        )

    [ticket_cost] => 66
    [gold_cost] => 54
    [user_gold] => 4252
    [silver] => 22563
    [user_tickets] => 1085
    [amount_of_products] => 0,772,659,233,0,263
    [last_update_time] => 1502806719,1639282922,1639282923,1639282922,1502424000,1639282922
)
```

- `status_code`: `1` is Plinko is enabled. Otherwise shows a generic dialog.
- `tiers`: This maps the award tiers to the indexes of the UI.
  - Tier 1 => Diamond Chest
  - Tier 2 => Gold Chest
  - Tier 3 => Silver Chest
  - Tier 4 => Bronze Chest
  - Tier 5 => 60-tickets
  - Tier 6 => 30-tickets
- `ticket_cost`: The cost in Plinko Tickets for a single puck drop.
- `gold_cost`: The cost in Gold Coins for a single puck drop.
- `user_gold`: The current amount of Gold Coins the user has.
- `silver`: The current amount of Silver Coins that the user has.
- `user_tickets`: The current amount of Plinko Tickets the player has.
- `amount_of_products`: This appears to be the total number of products available for chest tiers. `0` for ticket tiers.
- `last_update_time`: Shows the time when the tiers were last changed. This appears to be used to show the
                      'new' tooltip if the update time is newer than the last update.
                      

## /master/ticketexchange

This is called whenever opening the ticket redemption page.

### Request

```
POST /master/ticketexchange/ HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 39
Content-Type: application/x-www-form-urlencoded

cookie=8594ebfe66007296fd36e92319d67be6
```

### Response

```
a:3:{s:11:"status_code";i:51;s:5:"items";a:12:{i:0;a:6:{s:2:"id";s:1:"1";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"1792";s:4:"name";s:11:"Super-Taunt";s:4:"type";s:4:"Misc";s:10:"local_path";s:35:"/ui/fe2/store/icons/taunt_super.tga";}i:1;a:6:{s:2:"id";s:1:"2";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"2740";s:4:"name";s:21:"Hero_Fade.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:33:"/heroes/fade/trophy_skin/icon.tga";}i:2;a:6:{s:2:"id";s:1:"3";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"2840";s:4:"name";s:21:"Hero_Hiro.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:33:"/heroes/hiro/trophy_skin/icon.tga";}i:3;a:6:{s:2:"id";s:1:"4";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"2898";s:4:"name";s:31:"Hero_FlintBeastwood.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:44:"/heroes/flint_beastwood/trophy_skin/icon.tga";}i:4;a:6:{s:2:"id";s:1:"5";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"2944";s:4:"name";s:29:"Hero_MasterOfArms.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:43:"/heroes/master_of_arms/trophy_skin/icon.tga";}i:5;a:6:{s:2:"id";s:1:"6";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"3009";s:4:"name";s:25:"Hero_Solstice.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:37:"/heroes/solstice/trophy_skin/icon.tga";}i:6;a:6:{s:2:"id";s:1:"7";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"3075";s:4:"name";s:25:"Hero_Valkyrie.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:37:"/heroes/valkyrie/trophy_skin/icon.tga";}i:7;a:6:{s:2:"id";s:1:"8";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"3113";s:4:"name";s:27:"Hero_Pyromancer.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:39:"/heroes/pyromancer/trophy_skin/icon.tga";}i:8;a:6:{s:2:"id";s:1:"9";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"3191";s:4:"name";s:19:"Hero_Ra.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:31:"/heroes/ra/trophy_skin/icon.tga";}i:9;a:6:{s:2:"id";s:2:"10";s:4:"cost";s:4:"1300";s:10:"product_id";s:4:"3241";s:4:"name";s:23:"Hero_Magmar.trophy_skin";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:35:"/heroes/magmar/trophy_skin/icon.tga";}i:10;a:6:{s:2:"id";s:2:"11";s:4:"cost";s:3:"700";s:10:"product_id";s:4:"5397";s:4:"name";s:19:"Hero_Andromeda.Alt6";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:31:"/heroes/andromeda/alt6/icon.tga";}i:11;a:6:{s:2:"id";s:2:"12";s:4:"cost";s:3:"700";s:10:"product_id";s:4:"5397";s:4:"name";s:19:"Hero_Andromeda.Alt6";s:4:"type";s:10:"Alt Avatar";s:10:"local_path";s:31:"/heroes/andromeda/alt6/icon.tga";}}s:12:"user_tickets";s:4:"1085";}
```

```
Array
(
    [status_code] => 51
    [items] => Array
        (
            [0] => Array
                (
                    [id] => 1
                    [cost] => 1300
                    [product_id] => 1792
                    [name] => Super-Taunt
                    [type] => Misc
                    [local_path] => /ui/fe2/store/icons/taunt_super.tga
                )

            [1] => Array
                (
                    [id] => 2
                    [cost] => 1300
                    [product_id] => 2740
                    [name] => Hero_Fade.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/fade/trophy_skin/icon.tga
                )

            [2] => Array
                (
                    [id] => 3
                    [cost] => 1300
                    [product_id] => 2840
                    [name] => Hero_Hiro.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/hiro/trophy_skin/icon.tga
                )

            [3] => Array
                (
                    [id] => 4
                    [cost] => 1300
                    [product_id] => 2898
                    [name] => Hero_FlintBeastwood.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/flint_beastwood/trophy_skin/icon.tga
                )

            [4] => Array
                (
                    [id] => 5
                    [cost] => 1300
                    [product_id] => 2944
                    [name] => Hero_MasterOfArms.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/master_of_arms/trophy_skin/icon.tga
                )

            [5] => Array
                (
                    [id] => 6
                    [cost] => 1300
                    [product_id] => 3009
                    [name] => Hero_Solstice.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/solstice/trophy_skin/icon.tga
                )

            [6] => Array
                (
                    [id] => 7
                    [cost] => 1300
                    [product_id] => 3075
                    [name] => Hero_Valkyrie.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/valkyrie/trophy_skin/icon.tga
                )

            [7] => Array
                (
                    [id] => 8
                    [cost] => 1300
                    [product_id] => 3113
                    [name] => Hero_Pyromancer.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/pyromancer/trophy_skin/icon.tga
                )

            [8] => Array
                (
                    [id] => 9
                    [cost] => 1300
                    [product_id] => 3191
                    [name] => Hero_Ra.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/ra/trophy_skin/icon.tga
                )

            [9] => Array
                (
                    [id] => 10
                    [cost] => 1300
                    [product_id] => 3241
                    [name] => Hero_Magmar.trophy_skin
                    [type] => Alt Avatar
                    [local_path] => /heroes/magmar/trophy_skin/icon.tga
                )

            [10] => Array
                (
                    [id] => 11
                    [cost] => 700
                    [product_id] => 5397
                    [name] => Hero_Andromeda.Alt6
                    [type] => Alt Avatar
                    [local_path] => /heroes/andromeda/alt6/icon.tga
                )

            [11] => Array
                (
                    [id] => 12
                    [cost] => 700
                    [product_id] => 5397
                    [name] => Hero_Andromeda.Alt6
                    [type] => Alt Avatar
                    [local_path] => /heroes/andromeda/alt6/icon.tga
                )

        )

    [user_tickets] => 1085
)
```

- `status_code`: `51` indicates success. Any other value will show an error dialog.
- `items`: The array of available items for ticket redemption.
   - `id`: A unique identifier for the item. This appears to be a 1-based index to ensure uniqueness.
   - `cost`: The cost (in Plinko Tickets) for the item.
   - `productID`: The ID of the product.
   - `name`: The name of the product (e.g. `Hero_Andromeda.Alt6`)
   - `type`: The category (e.g. `Alt Avatar`, `Alt Announcement`, `Misc`, etc.)
   - `local_path`: The local path to the tga texture for the item.
- `user_tickets`: The number of tickets that the user currently has.

## /master/ticketexchange/purchase/

This endpoint is used to confirm a purchase in the ticket redemption page.

### Request

Example request where I bought `Trophy Swiftblade` alt avatar

```
POST /master/ticketexchange/purchase/ HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 47
Content-Type: application/x-www-form-urlencoded

cookie=8594ebfe66007296fd36e92319d67be6&id=2840
```

- `cookie`: The user's cookie for the current session.
- `id`: The product ID of the item to purchase. (e.g. `2840` maps to Trophy Swiftblade)

### Response

```
a:3:{s:11:"status_code";s:2:"51";s:17:"tickets_remaining";i:1;s:7:"grabBag";b:0;}
```

```
Array
(
    [status_code] => 51
    [tickets_remaining] => 1
    [grabBag] => 
)
```

- `status_code`: `51` indicates success. Any other value results in an error.
- `tickets_remaining`: The number of tickets the user has left after the purchase.
- `grabBag`: 

It's unclear to me how the grab bags work. Most of this is inferred from `game/ui/scripts/grabbag.lua`.

They seems to take the following arguments:

- `grabBag`: A boolean indicating whether or not this prize is a grab bag.
- `grabBagTheme`: The grab bag theme
  - `default`
  - `christmas`
  - `esports`
  - `celebrate`
  - `halloween`
- `grabBagIDs`: A `|`-delimited list of product IDs inside the grab bag.
- `grabBagNames`:  A `|`-delimited list of product names inside the grab bag.
- `grabBagPaths`:  A `|`-delimited list of local paths to the tga files for the items inside the grab bag.
- `grabBagTypes`: A `|`-delimited list of product types inside the grab bag (e.g. "Alt Avatar", "Couriers", "Misc", etc.)

## /master/casino/drop/

This is called whenever the user pays to play plinko (with either Tickets or Gold Coins).

This signals to the server to return the outcome of the game.

### Request

```
POST /master/casino/drop/ HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 56
Content-Type: application/x-www-form-urlencoded

cookie=8594ebfe66007296fd36e92319d67be6&currency=tickets
```

- `cookie`: The user's cookie.
- `currency`: Which currency the user selected. Either `tickets` (for Plinko Tickets) or `gold` (for Gold Coins).

### Response

- `user_tickets`: The user's remaining tickets (after the drop).
- `user_gold`: The user's remaining gold coins (after the drop).
- `status_code`: `1` indicates success. Any other value will trigger an error dialog.
- `random_tier`: The award tier that the user's drop resulted in.
  - Tier 1 => Diamond Chest
  - Tier 2 => Gold Chest
  - Tier 3 => Silver Chest
  - Tier 4 => Bronze Chest
  - Tier 5 => 60-tickets
  - Tier 6 => 30-tickets
- `product_id`: The ID of the product (or `-1` if the result was tickets).
- `product_name`: The name of the product (e.g. `Hero_Scout.Alt7`) or `Ticket` if the result was tickets.
- `product_type`: The type of the product (e.g. `Alt Avatar`, `Alt Announcement`, `Misc`, etc.) or `Ticket` if the result was tickets.
- `product_path`: The local path to the product's tga file. or `Ticket` if the result was tickets.
- `products_exhausted`: A boolean indicating whether or not the products been exhausted
                        -- i.e. the player already won on the prizes in that tier. When
                        this occurs, the player should just be awarded more tickets. (NOTE:
                        I can't seem to find where the game handles awarding tickets in this
                        case, so we may need to do it manually in our backend.)
- `ticket_amount`: The amount of tickets won (if the player hit a ticket tier. otherwise `0`).

#### Winning an Avatar

In this example response, I won the `Halflink Warrior` Scout avatar.

```
a:10:{s:12:"user_tickets";s:3:"911";s:9:"user_gold";s:4:"4252";s:11:"status_code";s:1:"1";s:11:"random_tier";s:1:"4";s:10:"product_id";s:4:"2736";s:12:"product_name";s:15:"Hero_Scout.Alt7";s:12:"product_type";s:10:"Alt Avatar";s:12:"product_path";s:27:"/heroes/scout/alt7/icon.tga";s:18:"products_exhausted";b:0;s:13:"ticket_amount";i:0;}
```

```
Array
(
    [user_tickets] => 911
    [user_gold] => 4252
    [status_code] => 1
    [random_tier] => 4
    [product_id] => 2736
    [product_name] => Hero_Scout.Alt7
    [product_type] => Alt Avatar
    [product_path] => /heroes/scout/alt7/icon.tga
    [products_exhausted] => 
    [ticket_amount] => 0
)
```

#### Winning 60-tickets

```
a:10:{s:12:"user_tickets";s:4:"1031";s:9:"user_gold";i:3982;s:11:"status_code";s:1:"1";s:11:"random_tier";s:1:"5";s:10:"product_id";s:2:"-1";s:12:"product_name";s:6:"Ticket";s:12:"product_type";s:6:"Ticket";s:12:"product_path";s:6:"Ticket";s:18:"products_exhausted";b:0;s:13:"ticket_amount";s:2:"60";}
```

```
Array
(
    [user_tickets] => 1031
    [user_gold] => 3982
    [status_code] => 1
    [random_tier] => 5
    [product_id] => -1
    [product_name] => Ticket
    [product_type] => Ticket
    [product_path] => Ticket
    [products_exhausted] => 
    [ticket_amount] => 60
)
```

#### Winning an Announcer

```
a:10:{s:12:"user_tickets";s:4:"1061";s:9:"user_gold";i:3874;s:11:"status_code";s:1:"1";s:11:"random_tier";s:1:"1";s:10:"product_id";s:4:"3939";s:12:"product_name";s:24:"Ascension Announcer Pack";s:12:"product_type";s:16:"Alt Announcement";s:12:"product_path";s:43:"/ui/fe2/store/icons/announcer_ascension.tga";s:18:"products_exhausted";b:0;s:13:"ticket_amount";i:0;}
```

```
Array
(
    [user_tickets] => 1061
    [user_gold] => 3874
    [status_code] => 1
    [random_tier] => 1
    [product_id] => 3939
    [product_name] => Ascension Announcer Pack
    [product_type] => Alt Announcement
    [product_path] => /ui/fe2/store/icons/announcer_ascension.tga
    [products_exhausted] => 
    [ticket_amount] => 0
)
```

## /master/casino/viewchest

### Request

```
POST /master/casino/viewchest/ HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 64
Content-Type: application/x-www-form-urlencoded

cookie=8594ebfe66007296fd36e92319d67be6&tier_id=3&target_index=1
```

- `cookie`: The user's cookie.
- `tier_id`: The tier of the chest to view the rewards for
  - Tier 1 => Diamond Chest
  - Tier 2 => Gold Chest
  - Tier 3 => Silver Chest
  - Tier 4 => Bronze Chest
- `target_index`: The 'page' index of the rewards, starting at index `1`.

### Response

- `tier_id`: The tier of the chest to view the rewards for
  - Tier 1 => Diamond Chest
  - Tier 2 => Gold Chest
  - Tier 3 => Silver Chest
  - Tier 4 => Bronze Chest
- `items_amount`: The number of items on this response. Interstingly plinko only shows 4 items per-page, but the results here return up to 56 results.
                  The client stores these locally in a table, to minimize network requests I imagine.
- `first_item_index`: The individual item index that started this result set. This value is out of all items available in this tier.
- `target_index`: The target item index from the request, which is contained in this result set.
- `product_names`: A comma-separated list of product names for each product available in this result set. 
- `product_types`: A comma-separated list of product type prefixes for each product available in this result set.
- `product_paths`:  A comma-separated list of local paths to the tga file for each product available in this result set.
- `product_ids`: A comma-separated list of the product IDs for each product in this result set.

#### Silver Chest - Page 1

```
a:8:{s:7:"tier_id";i:3;s:12:"items_amount";i:56;s:16:"first_item_index";i:1;s:12:"target_index";i:1;s:13:"product_names";s:1046:"Hero_Javaras.Alt9,Hero_Valkyrie.Alt13,Hero_Adrenaline.Alt6,Hero_Chronos.Alt11,Hero_Fairy.Alt7,Hero_Maliken.Alt9,Hero_Hiro.Alt14,Hero_Kraken.Alt6,Hero_Solstice.Alt11,Hero_Pyromancer.Alt10,Hero_Kane.Alt12,Poker_Taunt,Hero_SandWraith.Alt11,Hero_Ellonia.Alt8,Hero_Predator.Alt14,Hero_Ebulus.Alt8,Hero_Riptide.Alt8,Hero_Fade.Alt9,World Cup Soccer TP,2018 World Cup Announcer,Hero_Scar.Alt8,Hero_Dampeer.Alt10,Hero_Bubbles.Alt15,Hero_Prophet.Alt9,Hero_Andromeda.Alt6,Hero_Tarot.Alt10,Hero_Vanya.Alt7,Hero_Sapphire.Alt3,Forsaken_Taunt,Hero_Voodoo.Alt8,Hero_Hiro.Alt13,Hero_Mumra.Alt8,Hero_Mumra.Alt7,Hero_SirBenzington.Alt13,Hero_SirBenzington.Alt12,Hero_Dreadknight.Alt10,Hero_Dreadknight.Alt9,Hero_Goldenveil.Alt4,Hero_Goldenveil.Alt3,Hero_Nomad.Alt15,Hero_Vindicator.Alt11,Hero_Nomad.Alt14,Songkran_Taunt,Hero_Nomad.Alt13,Hero_Hunter.Alt12,Hero_DwarfMagi.Alt7,Hero_Gladiator.Alt12,Hero_Prophet.Alt8,Hero_Pyromancer.Alt9,Hero_Kenisis.Alt7,Hero_Rocky.Alt12,Hero_Hydromancer.Alt9,Hero_Devourer.Alt15,Hero_WitchSlayer.Alt11,candycane,Hero_Goldenveil.Alt2";s:13:"product_types";s:164:"aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,te,av,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,cc,aa";s:13:"product_paths";s:1747:"/heroes/javaras/alt9/icon.tga,/heroes/valkyrie/alt13/icon.tga,/heroes/adrenaline/alt6/icon.tga,/heroes/chronos/alt11/icon.tga,/heroes/fairy/alt7/icon.tga,/heroes/maliken/alt9/icon.tga,/heroes/hiro/alt14/icon.tga,/heroes/kraken/alt6/icon.tga,/heroes/solstice/alt11/icon.tga,/heroes/pyromancer/alt10/icon.tga,/heroes/kane/alt12/icon.tga,/ui/fe2/store/icons/taunt_poker.tga,/heroes/sand_wraith/alt11/icon.tga,/heroes/ellonia/alt8/icon.tga,/heroes/predator/alt14/icon.tga,heroes/ebulus/alt8/icon.tga,/heroes/riptide/alt8/icon.tga,/heroes/fade/alt9/icon.tga,/ui/fe2/store/icons/tp_worldcup.tga,/ui/fe2/store/icons/announcer_2018wc.tga,/heroes/scar/alt8/icon.tga,/heroes/dampeer/alt10/icon.tga,/heroes/bubbles/alt15/icon.tga,/heroes/prophet/alt9/icon.tga,/heroes/andromeda/alt6/icon.tga,/heroes/tarot/alt10/icon.tga,,/heroes/sapphire/alt3/icon.tga,/ui/fe2/store/icons/taunt_Shikigami.tga,/heroes/voodoo/alt8/icon.tga,/heroes/hiro/alt13/icon.tga,/heroes/mumra/alt7/icon.tga,/heroes/mumra/alt7/icon.tga,/heroes/sir_benzington/alt12/icon.tga,/heroes/sir_benzington/alt12/icon.tga,/heroes/dreadknight/alt9/icon.tga,/heroes/dreadknight/alt9/icon.tga,/heroes/goldenveil/alt3/icon.tga,/heroes/goldenveil/alt3/icon.tga,/heroes/nomad/alt13/icon.tga,/heroes/vindicator/alt11/icon.tga,/heroes/nomad/alt14/icon.tga,/ui/fe2/store/icons/taunt_songkran.tga,/heroes/nomad/alt13/icon.tga,/heroes/hunter/alt12/icon.tga,/heroes/dwarf_magi/alt7/icon.tga,/heroes/gladiator/alt12/icon.tga,/heroes/prophet/alt8/icon.tga,/heroes/pyromancer/alt9/icon.tga,/heroes/kenisis/alt7/icon.tga,/heroes/rocky/alt12/icon.tga,/heroes/hydromancer/alt9/icon.tga,/heroes/devourer/alt15/icon.tga,/heroes/witch_slayer/alt11/icon.tga,/ui/icons/candycane_color.tga,/heroes/goldenveil/alt2/icon.tga";s:11:"product_ids";s:279:"5674,5672,5670,5611,5609,5607,5603,5586,5546,5544,5542,5534,5532,5530,5509,5507,5474,5472,5458,5457,5449,5447,5409,5407,5397,5395,5393,5391,5377,5361,5359,5341,5340,5338,5337,5335,5334,5332,5331,5315,5296,5294,5293,5290,5273,5248,5244,5239,5237,5235,5219,5213,5211,5209,5185,5172";}
```

```
Array
(
    [tier_id] => 3
    [items_amount] => 56
    [first_item_index] => 1
    [target_index] => 1
    [product_names] => Hero_Javaras.Alt9,Hero_Valkyrie.Alt13,Hero_Adrenaline.Alt6,Hero_Chronos.Alt11,Hero_Fairy.Alt7,Hero_Maliken.Alt9,Hero_Hiro.Alt14,Hero_Kraken.Alt6,Hero_Solstice.Alt11,Hero_Pyromancer.Alt10,Hero_Kane.Alt12,Poker_Taunt,Hero_SandWraith.Alt11,Hero_Ellonia.Alt8,Hero_Predator.Alt14,Hero_Ebulus.Alt8,Hero_Riptide.Alt8,Hero_Fade.Alt9,World Cup Soccer TP,2018 World Cup Announcer,Hero_Scar.Alt8,Hero_Dampeer.Alt10,Hero_Bubbles.Alt15,Hero_Prophet.Alt9,Hero_Andromeda.Alt6,Hero_Tarot.Alt10,Hero_Vanya.Alt7,Hero_Sapphire.Alt3,Forsaken_Taunt,Hero_Voodoo.Alt8,Hero_Hiro.Alt13,Hero_Mumra.Alt8,Hero_Mumra.Alt7,Hero_SirBenzington.Alt13,Hero_SirBenzington.Alt12,Hero_Dreadknight.Alt10,Hero_Dreadknight.Alt9,Hero_Goldenveil.Alt4,Hero_Goldenveil.Alt3,Hero_Nomad.Alt15,Hero_Vindicator.Alt11,Hero_Nomad.Alt14,Songkran_Taunt,Hero_Nomad.Alt13,Hero_Hunter.Alt12,Hero_DwarfMagi.Alt7,Hero_Gladiator.Alt12,Hero_Prophet.Alt8,Hero_Pyromancer.Alt9,Hero_Kenisis.Alt7,Hero_Rocky.Alt12,Hero_Hydromancer.Alt9,Hero_Devourer.Alt15,Hero_WitchSlayer.Alt11,candycane,Hero_Goldenveil.Alt2
    [product_types] => aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,te,av,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,t,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,aa,cc,aa
    [product_paths] => /heroes/javaras/alt9/icon.tga,/heroes/valkyrie/alt13/icon.tga,/heroes/adrenaline/alt6/icon.tga,/heroes/chronos/alt11/icon.tga,/heroes/fairy/alt7/icon.tga,/heroes/maliken/alt9/icon.tga,/heroes/hiro/alt14/icon.tga,/heroes/kraken/alt6/icon.tga,/heroes/solstice/alt11/icon.tga,/heroes/pyromancer/alt10/icon.tga,/heroes/kane/alt12/icon.tga,/ui/fe2/store/icons/taunt_poker.tga,/heroes/sand_wraith/alt11/icon.tga,/heroes/ellonia/alt8/icon.tga,/heroes/predator/alt14/icon.tga,heroes/ebulus/alt8/icon.tga,/heroes/riptide/alt8/icon.tga,/heroes/fade/alt9/icon.tga,/ui/fe2/store/icons/tp_worldcup.tga,/ui/fe2/store/icons/announcer_2018wc.tga,/heroes/scar/alt8/icon.tga,/heroes/dampeer/alt10/icon.tga,/heroes/bubbles/alt15/icon.tga,/heroes/prophet/alt9/icon.tga,/heroes/andromeda/alt6/icon.tga,/heroes/tarot/alt10/icon.tga,,/heroes/sapphire/alt3/icon.tga,/ui/fe2/store/icons/taunt_Shikigami.tga,/heroes/voodoo/alt8/icon.tga,/heroes/hiro/alt13/icon.tga,/heroes/mumra/alt7/icon.tga,/heroes/mumra/alt7/icon.tga,/heroes/sir_benzington/alt12/icon.tga,/heroes/sir_benzington/alt12/icon.tga,/heroes/dreadknight/alt9/icon.tga,/heroes/dreadknight/alt9/icon.tga,/heroes/goldenveil/alt3/icon.tga,/heroes/goldenveil/alt3/icon.tga,/heroes/nomad/alt13/icon.tga,/heroes/vindicator/alt11/icon.tga,/heroes/nomad/alt14/icon.tga,/ui/fe2/store/icons/taunt_songkran.tga,/heroes/nomad/alt13/icon.tga,/heroes/hunter/alt12/icon.tga,/heroes/dwarf_magi/alt7/icon.tga,/heroes/gladiator/alt12/icon.tga,/heroes/prophet/alt8/icon.tga,/heroes/pyromancer/alt9/icon.tga,/heroes/kenisis/alt7/icon.tga,/heroes/rocky/alt12/icon.tga,/heroes/hydromancer/alt9/icon.tga,/heroes/devourer/alt15/icon.tga,/heroes/witch_slayer/alt11/icon.tga,/ui/icons/candycane_color.tga,/heroes/goldenveil/alt2/icon.tga
    [product_ids] => 5674,5672,5670,5611,5609,5607,5603,5586,5546,5544,5542,5534,5532,5530,5509,5507,5474,5472,5458,5457,5449,5447,5409,5407,5397,5395,5393,5391,5377,5361,5359,5341,5340,5338,5337,5335,5334,5332,5331,5315,5296,5294,5293,5290,5273,5248,5244,5239,5237,5235,5219,5213,5211,5209,5185,5172
)
```

#### Silver Chest - Page 193

```
a:8:{s:7:"tier_id";i:3;s:12:"items_amount";i:32;s:16:"first_item_index";i:741;s:12:"target_index";i:769;s:13:"product_names";s:524:"Hero_Hydromancer.Alt2,Hero_Mumra.Alt2,Hero_DwarfMagi.Alt2,Hero_Dampeer.Alt2,Hero_Hantumon.Alt2,Hero_EmeraldWarden.Alt2,Hero_Ra.Alt2,Hero_Bubbles.Alt2,Hero_Yogi.Alt,emerald,Hero_Hunter.Alt,Hero_Midas.Alt2,Hero_Chronos.Alt2,Hero_Panda.Alt,Hero_DoctorRepulsor.Alt,Hero_CorruptedDisciple.Alt,Hero_Zephyr.Alt2,BreakyCPK,Hero_Deadwood.Alt2,Hero_Cthulhuphant.Alt,British,Hero_FlintBeastwood.Alt2,tanzanite,Hero_Predator.Alt,Hero_BabaYaga.Alt,Hero_Maliken.Alt3,Hero_Deadwood.Alt,Hero_Treant.Alt,diamond,white,Flamboyant,silvershield";s:13:"product_types";s:95:"aa,aa,aa,aa,aa,aa,aa,aa,aa,cc,aa,aa,aa,aa,aa,aa,aa,av,aa,aa,av,aa,cc,aa,aa,aa,aa,aa,cc,cc,av,cc";s:13:"product_paths";s:991:"/heroes/hydromancer/alt2/icon.tga,/heroes/mumra/alt2/icon.tga,/heroes/dwarf_magi/alt2/icon.tga,/heroes/dampeer/alt2/icon.tga,/heroes/hantumon/alt2/icon.tga,/heroes/emerald_warden/alt2/icon.tga,/heroes/ra/alt2/icon.tga,/heroes/bubbles/alt2/icon.tga,/heroes/yogi/alt/icon.tga,/ui/icons/emerald.tga,/heroes/hunter/alt/icon.tga,/heroes/midas/alt2/icon.tga,/heroes/chronos/alt2/icon.tga,/heroes/panda/alt/icon.tga,/heroes/doctor_repulsor/alt/icon.tga,/heroes/corrupted_disciple/alt/icon.tga,/heroes/zephyr/alt2/icon.tga,/ui/fe2/store/icons/announcer_breaky.tga,/heroes/deadwood/alt2/icon.tga,heroes/cthulhuphant/icon.tga,/ui/fe2/store/icons/announcer_english.tga,heroes/flint_beastwood/alt2/icon.tga,/ui/icons/tanzanite.tga,/heroes/predator/alt/icon.tga,/heroes/babayaga/alt/icon.tga,/heroes/maliken/alt3/icon.tga,/heroes/deadwood/alt/icon.tga,/heroes/treant/alt/icon.tga,ui/icons/diamond.tga,/ui/legion/ability_coverup.tga,/ui/common/models/unicorn/icon.tga,/ui/fe2/store/icons/silver_shield.tga";s:11:"product_ids";s:126:"968,966,963,961,954,946,938,936,934,925,923,921,913,911,900,897,891,890,885,849,664,656,564,456,454,253,252,251,185,179,164,21";}
```

```
Array
(
    [tier_id] => 3
    [items_amount] => 32
    [first_item_index] => 741
    [target_index] => 769
    [product_names] => Hero_Hydromancer.Alt2,Hero_Mumra.Alt2,Hero_DwarfMagi.Alt2,Hero_Dampeer.Alt2,Hero_Hantumon.Alt2,Hero_EmeraldWarden.Alt2,Hero_Ra.Alt2,Hero_Bubbles.Alt2,Hero_Yogi.Alt,emerald,Hero_Hunter.Alt,Hero_Midas.Alt2,Hero_Chronos.Alt2,Hero_Panda.Alt,Hero_DoctorRepulsor.Alt,Hero_CorruptedDisciple.Alt,Hero_Zephyr.Alt2,BreakyCPK,Hero_Deadwood.Alt2,Hero_Cthulhuphant.Alt,British,Hero_FlintBeastwood.Alt2,tanzanite,Hero_Predator.Alt,Hero_BabaYaga.Alt,Hero_Maliken.Alt3,Hero_Deadwood.Alt,Hero_Treant.Alt,diamond,white,Flamboyant,silvershield
    [product_types] => aa,aa,aa,aa,aa,aa,aa,aa,aa,cc,aa,aa,aa,aa,aa,aa,aa,av,aa,aa,av,aa,cc,aa,aa,aa,aa,aa,cc,cc,av,cc
    [product_paths] => /heroes/hydromancer/alt2/icon.tga,/heroes/mumra/alt2/icon.tga,/heroes/dwarf_magi/alt2/icon.tga,/heroes/dampeer/alt2/icon.tga,/heroes/hantumon/alt2/icon.tga,/heroes/emerald_warden/alt2/icon.tga,/heroes/ra/alt2/icon.tga,/heroes/bubbles/alt2/icon.tga,/heroes/yogi/alt/icon.tga,/ui/icons/emerald.tga,/heroes/hunter/alt/icon.tga,/heroes/midas/alt2/icon.tga,/heroes/chronos/alt2/icon.tga,/heroes/panda/alt/icon.tga,/heroes/doctor_repulsor/alt/icon.tga,/heroes/corrupted_disciple/alt/icon.tga,/heroes/zephyr/alt2/icon.tga,/ui/fe2/store/icons/announcer_breaky.tga,/heroes/deadwood/alt2/icon.tga,heroes/cthulhuphant/icon.tga,/ui/fe2/store/icons/announcer_english.tga,heroes/flint_beastwood/alt2/icon.tga,/ui/icons/tanzanite.tga,/heroes/predator/alt/icon.tga,/heroes/babayaga/alt/icon.tga,/heroes/maliken/alt3/icon.tga,/heroes/deadwood/alt/icon.tga,/heroes/treant/alt/icon.tga,ui/icons/diamond.tga,/ui/legion/ability_coverup.tga,/ui/common/models/unicorn/icon.tga,/ui/fe2/store/icons/silver_shield.tga
    [product_ids] => 968,966,963,961,954,946,938,936,934,925,923,921,913,911,900,897,891,890,885,849,664,656,564,456,454,253,252,251,185,179,164,21
)
```