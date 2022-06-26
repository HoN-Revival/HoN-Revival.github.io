---
layout: default
title: client_requester.php?f=get_products
parent: PHP Endpoints
grand_parent: Master Server
---

# get_products

This appears to be a massive request when opening the shop to populate all of the
available products.

## Request

```
POST /client_requester.php?f=get_products HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 73
Content-Type: application/x-www-form-urlencoded

account_id=9146854&cookie=a20eab817a49f5ae42b270b782a71145&crc=2147483647
```

- `account_id`: The current user's account ID.
- `cookie`: The cookie for the user's session.
- `crc`: Unknown. Some kind of CRC check?

## Response

```
Array
(
    [products] => Array
        (
            [Alt Avatar] => Array
                (
                    [15] => Array
                        (
                            [name] => Hero_Pyromancer.Female
                            [cname] => Female Pyromancer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 90
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [16] => Array
                        (
                            [name] => Hero_Krixi.Sexy
                            [cname] => Sexy Moon Queen
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 90
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [17] => Array
                        (
                            [name] => Hero_PollywogPriest.Chieftain
                            [cname] => Pollywog Chieftain
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 90
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [18] => Array
                        (
                            [name] => Hero_Magmar.Scorpion
                            [cname] => Scorpion Magmus
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 90
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [19] => Array
                        (
                            [name] => Hero_Frosty.Female
                            [cname] => Female Glacius
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 90
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [176] => Array
                        (
                            [name] => Hero_Soulstealer.Alt
                            [cname] => Raven Soulstealer
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [180] => Array
                        (
                            [name] => Hero_Bombardier.Alt
                            [cname] => Cannon Bombardier
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [181] => Array
                        (
                            [name] => Hero_Scar.Scary
                            [cname] => Nightmare Madman
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [182] => Array
                        (
                            [name] => Hero_Devourer.Clown
                            [cname] => Clown Devourer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [183] => Array
                        (
                            [name] => Hero_Succubis.Angel
                            [cname] => Angelic Succubus
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [184] => Array
                        (
                            [name] => Hero_Succubis.Naughty
                            [cname] => Naughty Succubus
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [187] => Array
                        (
                            [name] => Hero_WitchSlayer.Pimp
                            [cname] => Pimp Slayer
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [188] => Array
                        (
                            [name] => Hero_Gauntlet.Alt
                            [cname] => El Guantelete
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [214] => Array
                        (
                            [name] => Hero_Bubbles.Alt
                            [cname] => Ninja Bubbles
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [231] => Array
                        (
                            [name] => Hero_Gladiator.Alt
                            [cname] => Adventure Gladiator
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [232] => Array
                        (
                            [name] => Hero_Hantumon.Alt
                            [cname] => Teen Hound
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [236] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt
                            [cname] => Captain Flint
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [251] => Array
                        (
                            [name] => Hero_Treant.Alt
                            [cname] => Christmas Keeper
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [252] => Array
                        (
                            [name] => Hero_Deadwood.Alt
                            [cname] => Jollywood
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [253] => Array
                        (
                            [name] => Hero_Maliken.Alt3
                            [cname] => Mali Klause
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [260] => Array
                        (
                            [name] => Hero_Dampeer.Alt
                            [cname] => Vacation Dampeer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [303] => Array
                        (
                            [name] => Hero_Arachna.Alt
                            [cname] => Queen Arachna
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [324] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt
                            [cname] => Helga Hammerstorm
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [339] => Array
                        (
                            [name] => Hero_Kraken.Alt
                            [cname] => Crustacean Kraken
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [358] => Array
                        (
                            [name] => Hero_HellDemon.Alt
                            [cname] => Grim Reaper
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [359] => Array
                        (
                            [name] => Hero_Hiro.Alt
                            [cname] => Sachi Swiftblade
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [378] => Array
                        (
                            [name] => Hero_Empath.Alt
                            [cname] => Mage Empath
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [411] => Array
                        (
                            [name] => Hero_Hellbringer.Alt
                            [cname] => Overseer Hellbringer
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [412] => Array
                        (
                            [name] => Hero_Tempest.Alt
                            [cname] => Mystic Tempest
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [422] => Array
                        (
                            [name] => Hero_Valkyrie.Alt
                            [cname] => Legendary Valkyrie
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [438] => Array
                        (
                            [name] => Hero_Rampage.Alt
                            [cname] => Unicorn Rampage
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [443] => Array
                        (
                            [name] => Hero_Ebulus.Alt
                            [cname] => MSIvy Slither
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [439] => Array
                        (
                            [name] => Hero_Rampage.Alt2
                            [cname] => Rainbow Rampage
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [441] => Array
                        (
                            [name] => Hero_Engineer.Alt
                            [cname] => Rosie Engineer
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [444] => Array
                        (
                            [name] => Hero_Tundra.Alt
                            [cname] => Mountain Tundra
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [445] => Array
                        (
                            [name] => Hero_Tremble.Alt
                            [cname] => Quadropod Tremble
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [449] => Array
                        (
                            [name] => Hero_Nomad.Alt
                            [cname] => Nomaddin
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [451] => Array
                        (
                            [name] => Hero_Pestilence.Alt
                            [cname] => Ladybug Pestilence
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [454] => Array
                        (
                            [name] => Hero_BabaYaga.Alt
                            [cname] => Wretched Hottie
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [455] => Array
                        (
                            [name] => Hero_Silhouette.Alt
                            [cname] => White Lotus Silhouette
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [456] => Array
                        (
                            [name] => Hero_Predator.Alt
                            [cname] => Bunny Predator
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [474] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt
                            [cname] => Forsaken Strider
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [476] => Array
                        (
                            [name] => Hero_Flux.Alt
                            [cname] => Steam Flux
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [483] => Array
                        (
                            [name] => Hero_Vindicator.Alt
                            [cname] => Vigilante Vindicator
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [493] => Array
                        (
                            [name] => Hero_Armadon.Alt
                            [cname] => Winston Charmadon
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [494] => Array
                        (
                            [name] => Hero_Kunas.Alt
                            [cname] => Thor Thunderbringer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [496] => Array
                        (
                            [name] => Hero_Rocky.Alt
                            [cname] => Golden Pebbles
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [506] => Array
                        (
                            [name] => Hero_Hydromancer.Alt
                            [cname] => Mermaidon
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [509] => Array
                        (
                            [name] => Hero_Devourer.Alt2
                            [cname] => Oni Devourer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [520] => Array
                        (
                            [name] => Hero_Ra.Alt
                            [cname] => King Ra
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [524] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt
                            [cname] => Leprechaun Blacksmith
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [525] => Array
                        (
                            [name] => Hero_Parasite.Alt
                            [cname] => Mutant Parasite
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [546] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt
                            [cname] => Dryad Warden
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [563] => Array
                        (
                            [name] => Hero_Defiler.Alt
                            [cname] => Phantom Defiler
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [656] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt2
                            [cname] => Flint Boomstick
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [668] => Array
                        (
                            [name] => Hero_Zephyr.Alt
                            [cname] => Snow Zephyr
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [669] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt
                            [cname] => Hillbilly Brawler
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [701] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt2
                            [cname] => Commander of Arms
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [702] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt
                            [cname] => Jade Warrior
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [708] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt
                            [cname] => Frost Rider
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [752] => Array
                        (
                            [name] => Hero_Geomancer.Alt
                            [cname] => Centipedalisk
                            [cost] => 640
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [753] => Array
                        (
                            [name] => Hero_Accursed.Alt
                            [cname] => Sub Zero Accursed
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [784] => Array
                        (
                            [name] => Hero_Scout.Alt
                            [cname] => Mist Runner Scout
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [835] => Array
                        (
                            [name] => Hero_Jereziah.Alt
                            [cname] => Dark Jeraziah
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [838] => Array
                        (
                            [name] => Hero_Midas.Alt
                            [cname] => Lord Midas
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [842] => Array
                        (
                            [name] => Hero_Legionnaire.Alt
                            [cname] => Logger Legionnaire
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [849] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt
                            [cname] => King Cthulhuphant
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [850] => Array
                        (
                            [name] => Hero_Chipper.Alt
                            [cname] => Mr. Chipper
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [854] => Array
                        (
                            [name] => Hero_Javaras.Alt
                            [cname] => Magus Bane
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [858] => Array
                        (
                            [name] => Hero_Behemoth.Alt
                            [cname] => Infernal Behemoth
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [861] => Array
                        (
                            [name] => Hero_Monarch.Alt
                            [cname] => Queen Monarch
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [869] => Array
                        (
                            [name] => Hero_Gladiator.Alt2
                            [cname] => Gladius Beardicus
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [873] => Array
                        (
                            [name] => Hero_Gemini.Alt
                            [cname] => Panthera Gemini
                            [cost] => 640
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [874] => Array
                        (
                            [name] => Hero_Hiro.Alt2
                            [cname] => Ronin Swiftblade
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [875] => Array
                        (
                            [name] => Hero_Rhapsody.Alt
                            [cname] => Death Metal Rhapsody
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [878] => Array
                        (
                            [name] => Hero_Mumra.Alt
                            [cname] => Cleopatra Pharaoh
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [879] => Array
                        (
                            [name] => Hero_Andromeda.Alt
                            [cname] => Mandromeda
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [883] => Array
                        (
                            [name] => Hero_Shaman.Alt
                            [cname] => Demented Witch
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [885] => Array
                        (
                            [name] => Hero_Deadwood.Alt2
                            [cname] => Flaming Deadwood
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [887] => Array
                        (
                            [name] => Hero_Revenant.Alt
                            [cname] => Wraith Revenant
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [888] => Array
                        (
                            [name] => Hero_Fairy.Alt
                            [cname] => Spriticus
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [891] => Array
                        (
                            [name] => Hero_Zephyr.Alt2
                            [cname] => Turkey Zephyr
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [894] => Array
                        (
                            [name] => Hero_Dreadknight.Alt
                            [cname] => Dreadknight Salforis
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [897] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt
                            [cname] => Steampunk Disciple
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [898] => Array
                        (
                            [name] => Hero_Chronos.Alt
                            [cname] => Father Time Chronos
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [900] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt
                            [cname] => Professor Repulsor
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [901] => Array
                        (
                            [name] => Hero_Valkyrie.Alt2
                            [cname] => Fallen Valkyrie
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [902] => Array
                        (
                            [name] => Hero_Martyr.Alt
                            [cname] => Sister Martyr
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [905] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt
                            [cname] => Corporeal Shadowblade
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [911] => Array
                        (
                            [name] => Hero_Panda.Alt
                            [cname] => Kangamonium
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [913] => Array
                        (
                            [name] => Hero_Chronos.Alt2
                            [cname] => Grandfather Time Chronos
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [916] => Array
                        (
                            [name] => Hero_Treant.Alt2
                            [cname] => Mother Nature Keeper
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [919] => Array
                        (
                            [name] => Hero_Xalynx.Alt
                            [cname] => Dominatrix Torturer
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [921] => Array
                        (
                            [name] => Hero_Midas.Alt2
                            [cname] => Santa Midas
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [923] => Array
                        (
                            [name] => Hero_Hunter.Alt
                            [cname] => LandShark Bloodhunter
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [932] => Array
                        (
                            [name] => Hero_Artesia.Alt
                            [cname] => Arcannis
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [934] => Array
                        (
                            [name] => Hero_Yogi.Alt
                            [cname] => Arctic Wild Soul
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [936] => Array
                        (
                            [name] => Hero_Bubbles.Alt2
                            [cname] => Patriot Bubbles
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [938] => Array
                        (
                            [name] => Hero_Ra.Alt2
                            [cname] => Phoenix Ra
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [940] => Array
                        (
                            [name] => Hero_Vanya.Alt
                            [cname] => Dark Zealot
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [945] => Array
                        (
                            [name] => Hero_Taint.Alt
                            [cname] => Shinigami Gravekeeper
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [946] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt2
                            [cname] => Jurassic Warden
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [949] => Array
                        (
                            [name] => Hero_Voodoo.Alt
                            [cname] => Voodoo Raptor
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [952] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt2
                            [cname] => Classic Pollywog Priest
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [954] => Array
                        (
                            [name] => Hero_Hantumon.Alt2
                            [cname] => Night Hunter
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [956] => Array
                        (
                            [name] => Hero_Fade.Alt
                            [cname] => Gypsy Fayde
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [961] => Array
                        (
                            [name] => Hero_Dampeer.Alt2
                            [cname] => Count Dampeer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [963] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt2
                            [cname] => Kuznya Blacksmith
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [966] => Array
                        (
                            [name] => Hero_Mumra.Alt2
                            [cname] => Golden Emperor
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [968] => Array
                        (
                            [name] => Hero_Hydromancer.Alt2
                            [cname] => Shenlong
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [973] => Array
                        (
                            [name] => Hero_Berzerker.Alt
                            [cname] => Chaos Berzerker
                            [cost] => 250
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [975] => Array
                        (
                            [name] => Hero_SandWraith.Alt
                            [cname] => Horseman Famine
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [977] => Array
                        (
                            [name] => Hero_WolfMan.Alt
                            [cname] => Horseman War
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [979] => Array
                        (
                            [name] => Hero_Dreadknight.Alt2
                            [cname] => Horseman Death
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [981] => Array
                        (
                            [name] => Hero_Pestilence.Alt2
                            [cname] => Horseman Pestilence
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [983] => Array
                        (
                            [name] => Hero_Maliken.Alt
                            [cname] => Horseman Conquest
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [985] => Array
                        (
                            [name] => Hero_Legionnaire.Alt2
                            [cname] => Golden Centurion
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [987] => Array
                        (
                            [name] => Hero_Predator.Alt2
                            [cname] => Xeno Predator
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [989] => Array
                        (
                            [name] => Hero_Succubis.Alt2
                            [cname] => Cupid
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [998] => Array
                        (
                            [name] => Hero_FlameDragon.Alt
                            [cname] => Hydraxis
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1001] => Array
                        (
                            [name] => Hero_Monarch.Alt2
                            [cname] => Queen Bee Monarch
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1007] => Array
                        (
                            [name] => Hero_Kenisis.Alt
                            [cname] => Zeta Kinesis
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1010] => Array
                        (
                            [name] => Hero_Electrician.Alt
                            [cname] => Demonbuster Electrician
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1012] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt2
                            [cname] => PeKing Duck
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1017] => Array
                        (
                            [name] => Hero_Gunblade.Alt
                            [cname] => Warmonger Gunblade
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1021] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt3
                            [cname] => Queen Of Fools
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1019] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt2
                            [cname] => Woolly Cthulhuphant
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1024] => Array
                        (
                            [name] => Hero_Gauntlet.Alt2
                            [cname] => O-yoroi Gauntlet
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1029] => Array
                        (
                            [name] => Hero_Blitz.Alt
                            [cname] => Celeris
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1031] => Array
                        (
                            [name] => Hero_Nomad.Alt2
                            [cname] => Shaka Nomad
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1033] => Array
                        (
                            [name] => Hero_Geomancer.Alt2
                            [cname] => Geojuice
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1035] => Array
                        (
                            [name] => Hero_Midas.Alt3
                            [cname] => Medusa Midas
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1037] => Array
                        (
                            [name] => Hero_Moraxus.Alt
                            [cname] => Chainsaw Moraxus
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1039] => Array
                        (
                            [name] => Hero_Magmar.Alt2
                            [cname] => Magmoose
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1041] => Array
                        (
                            [name] => Hero_Electrician.Alt2
                            [cname] => Steampunk Electrician
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1043] => Array
                        (
                            [name] => Hero_Aluna.Alt
                            [cname] => Stardust Aluna
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1045] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt2
                            [cname] => Clockwork Archer
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1047] => Array
                        (
                            [name] => Hero_Bephelgor.Alt2
                            [cname] => Crematorium Balph
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1049] => Array
                        (
                            [name] => Hero_Rampage.Alt3
                            [cname] => Rhino Rampage
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1051] => Array
                        (
                            [name] => Hero_Scout.Alt2
                            [cname] => Sniper Scout
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1057] => Array
                        (
                            [name] => Hero_Artillery.Alt
                            [cname] => Heavy Artillery
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1064] => Array
                        (
                            [name] => Hero_Ellonia.Alt
                            [cname] => Zero
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1066] => Array
                        (
                            [name] => Hero_Valkyrie.Alt3
                            [cname] => Cyber Valk
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1080] => Array
                        (
                            [name] => Hero_Behemoth.Alt2
                            [cname] => Minotaur Behemoth
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1157] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt2
                            [cname] => Witch Hunter
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1142] => Array
                        (
                            [name] => Hero_Riftmage.Alt
                            [cname] => Elder Riftwalker
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1144] => Array
                        (
                            [name] => Hero_Rocky.Alt2
                            [cname] => Jade Giant Pebbles
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1146] => Array
                        (
                            [name] => Hero_Kenisis.Alt2
                            [cname] => Kinesia
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1153] => Array
                        (
                            [name] => Hero_Plant.Alt
                            [cname] => Spike
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1155] => Array
                        (
                            [name] => Hero_Vindicator.Alt2
                            [cname] => Judge Vindicator
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1159] => Array
                        (
                            [name] => Hero_Bombardier.Alt2
                            [cname] => Zeppelin Bombadier
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1166] => Array
                        (
                            [name] => Hero_Ravenor.Alt
                            [cname] => Dominus Ravenor
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1168] => Array
                        (
                            [name] => Hero_Andromeda.Alt2
                            [cname] => Alien Andromeda
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1170] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt3
                            [cname] => The Orc With No Name
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1172] => Array
                        (
                            [name] => Hero_Ophelia.Alt
                            [cname] => Illithiphelia
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1185] => Array
                        (
                            [name] => Hero_FlameDragon.Alt2
                            [cname] => Chimera Draconis
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1187] => Array
                        (
                            [name] => Hero_Arachna.Alt2
                            [cname] => Brass Arachna
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1257] => Array
                        (
                            [name] => Hero_Prophet.Alt
                            [cname] => Serpent Prophet
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1194] => Array
                        (
                            [name] => Hero_Engineer.Alt2
                            [cname] => Uncle Sam Engineer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1197] => Array
                        (
                            [name] => Hero_Ophelia.Alt2
                            [cname] => Antphelia
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1200] => Array
                        (
                            [name] => Hero_Devourer.Alt3
                            [cname] => Shibo Shinobi
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1202] => Array
                        (
                            [name] => Hero_Silhouette.Alt2
                            [cname] => Master Assassin Sil
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1211] => Array
                        (
                            [name] => Hero_Tempest.main_reskin
                            [cname] => Phantom Tempest
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1213] => Array
                        (
                            [name] => Hero_Voodoo.Alt2
                            [cname] => Voodoo Doctor
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1215] => Array
                        (
                            [name] => Hero_Ebulus.Alt2
                            [cname] => Infected Slither
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1218] => Array
                        (
                            [name] => Hero_Hiro.Alt3
                            [cname] => Bushi Swiftblade
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1220] => Array
                        (
                            [name] => Hero_Berzerker.Alt2
                            [cname] => Demon Hunter Zerker
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1225] => Array
                        (
                            [name] => Hero_Rally.Alt
                            [cname] => Warlord Rally
                            [cost] => 250
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1227] => Array
                        (
                            [name] => Hero_Rally.Alt2
                            [cname] => Joan D'Rally
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1229] => Array
                        (
                            [name] => Hero_Dreadknight.Alt3
                            [cname] => Lord Thanatos
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1231] => Array
                        (
                            [name] => Hero_Valkyrie.Alt4
                            [cname] => Headhunter Valkyrie
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1233] => Array
                        (
                            [name] => Hero_Javaras.Alt2
                            [cname] => Rage Bane
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1235] => Array
                        (
                            [name] => Hero_Legionnaire.Alt3
                            [cname] => Executioner Legionnaire
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1237] => Array
                        (
                            [name] => Hero_Flux.Alt2
                            [cname] => Iron Flux
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1239] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt
                            [cname] => Doll Master
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1241] => Array
                        (
                            [name] => Hero_BabaYaga.Alt2
                            [cname] => Hocus Pocus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1243] => Array
                        (
                            [name] => Hero_Gemini.Alt2
                            [cname] => Mecha Gemini
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1245] => Array
                        (
                            [name] => Hero_Kraken.Alt2
                            [cname] => Submariner Kraken
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1247] => Array
                        (
                            [name] => Hero_Tundra.Alt2
                            [cname] => Tribal Tundra
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1249] => Array
                        (
                            [name] => Hero_Ravenor.Alt2
                            [cname] => Storm Demon Ravenor
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1258] => Array
                        (
                            [name] => Hero_Prophet.Alt2
                            [cname] => Bone Prophet
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1279] => Array
                        (
                            [name] => Hero_Krixi.main_reskin
                            [cname] => Blood Moon Queen
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1281] => Array
                        (
                            [name] => Hero_Parasite.Alt2
                            [cname] => Envy
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1283] => Array
                        (
                            [name] => Hero_Armadon.Alt2
                            [cname] => Sloth
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1285] => Array
                        (
                            [name] => Hero_Deadwood.main_reskin
                            [cname] => Icy Deadwood
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1286] => Array
                        (
                            [name] => Hero_Pyromancer.Alt2
                            [cname] => Scorcher
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1287] => Array
                        (
                            [name] => Hero_Bephelgor.Alt3
                            [cname] => Garbagore
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1291] => Array
                        (
                            [name] => Hero_Jereziah.Alt2
                            [cname] => Pride
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1297] => Array
                        (
                            [name] => Hero_Oogie.Alt
                            [cname] => Haka
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1300] => Array
                        (
                            [name] => Hero_Oogie.Alt2
                            [cname] => Kurukuru
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1303] => Array
                        (
                            [name] => Hero_MonkeyKing.main_reskin
                            [cname] => Harumon Monkey King
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1305] => Array
                        (
                            [name] => Hero_Gladiator.Alt3
                            [cname] => Musketeer Gladiator
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1307] => Array
                        (
                            [name] => Hero_Empath.Alt2
                            [cname] => Lust
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1309] => Array
                        (
                            [name] => Hero_ForsakenArcher.main_reskin
                            [cname] => Sabre Tooth Archer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1318] => Array
                        (
                            [name] => Hero_Soulstealer.Alt2
                            [cname] => Greed
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1312] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt2
                            [cname] => Wrath
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1314] => Array
                        (
                            [name] => Hero_Panda.main_reskin
                            [cname] => Polarmonium
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1316] => Array
                        (
                            [name] => Hero_Hantumon.Alt3
                            [cname] => Night Hoodlum
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1320] => Array
                        (
                            [name] => Hero_Fairy.main_reskin
                            [cname] => Unseelie Nymphora
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1326] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt2
                            [cname] => Karabas Barabas
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1328] => Array
                        (
                            [name] => Hero_Devourer.Alt4
                            [cname] => Gluttony
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1330] => Array
                        (
                            [name] => Hero_Behemoth.main_reskin
                            [cname] => Bone Behemoth
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1332] => Array
                        (
                            [name] => Hero_Bubbles.Alt3
                            [cname] => Futbol Bubbles
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1334] => Array
                        (
                            [name] => Hero_Gunblade.Alt2
                            [cname] => Pirate Gunblade
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1340] => Array
                        (
                            [name] => Hero_Solstice.Alt
                            [cname] => Mr. Tickles
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1343] => Array
                        (
                            [name] => Hero_Solstice.Alt2
                            [cname] => Duel
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1349] => Array
                        (
                            [name] => Hero_Hellbringer.Alt2
                            [cname] => Priestess Hellbringer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1400] => Array
                        (
                            [name] => Hero_Zephyr.Alt3
                            [cname] => Twista
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1351] => Array
                        (
                            [name] => Hero_Rocky.Alt3
                            [cname] => Frankie Pebbles
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1353] => Array
                        (
                            [name] => Hero_Gauntlet.main_reskin
                            [cname] => Mummy Gauntlet
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1355] => Array
                        (
                            [name] => Hero_Scar.Alt2
                            [cname] => Hook Madman
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1357] => Array
                        (
                            [name] => Hero_Succubis.main_reskin
                            [cname] => Dark Succubus
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1360] => Array
                        (
                            [name] => Hero_Hiro.Alt4
                            [cname] => Zenifir the Dark Elf 
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1362] => Array
                        (
                            [name] => Hero_Hunter.Alt2
                            [cname] => Baby Yaga
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1364] => Array
                        (
                            [name] => Hero_FlameDragon.main_reskin
                            [cname] => Dracolich Draconis
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1366] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt3
                            [cname] => Master of Bows
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1368] => Array
                        (
                            [name] => Hero_Xalynx.Alt2
                            [cname] => Cenobite Torturer
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1370] => Array
                        (
                            [name] => Hero_Frosty.Alt2
                            [cname] => Joven Glacius
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1372] => Array
                        (
                            [name] => Hero_Taint.Alt2
                            [cname] => Archlich Gravekeeper
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1374] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt2
                            [cname] => Reborn Disciple
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1376] => Array
                        (
                            [name] => Hero_Ra.Alt3
                            [cname] => Risen Ra
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1379] => Array
                        (
                            [name] => Hero_Pyromancer.Alt3
                            [cname] => Headless Horseman Pyromancer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1381] => Array
                        (
                            [name] => Hero_Predator.Alt3
                            [cname] => Creature Predator
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1388] => Array
                        (
                            [name] => Hero_Pearl.Alt
                            [cname] => Brann 
                            [cost] => 640
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1391] => Array
                        (
                            [name] => Hero_Pearl.Alt2
                            [cname] => Shadian
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1394] => Array
                        (
                            [name] => Hero_Geomancer.main_reskin
                            [cname] => Caterpillar Geomancer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1396] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt2
                            [cname] => Tesla the Mad Scientist
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1402] => Array
                        (
                            [name] => Hero_Jereziah.main_reskin
                            [cname] => Crusader Jeraziah
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1404] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt4
                            [cname] => Flint Spellslinger
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1407] => Array
                        (
                            [name] => Hero_Solstice.Alt3
                            [cname] => King Animus
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1410] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt3
                            [cname] => Holly Polly
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1412] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt3
                            [cname] => Centaur Warden
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1414] => Array
                        (
                            [name] => Hero_Devourer.main_reskin
                            [cname] => Patchwork Devourer
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1416] => Array
                        (
                            [name] => Hero_Artillery.Alt2
                            [cname] => Gunnar the Artillerist
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1419] => Array
                        (
                            [name] => Hero_Fade.Alt_reskin
                            [cname] => Glorious Fayde
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1421] => Array
                        (
                            [name] => Hero_Pestilence.Alt3
                            [cname] => Queen Serecta
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1431] => Array
                        (
                            [name] => Hero_Grinex.Alt2
                            [cname] => Gideon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1434] => Array
                        (
                            [name] => Hero_Grinex.Alt
                            [cname] => Slickz
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1438] => Array
                        (
                            [name] => Hero_Nomad.Alt3
                            [cname] => Red Raja
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1440] => Array
                        (
                            [name] => Hero_Vanya.Alt2
                            [cname] => Hachina
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1442] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt3
                            [cname] => Royal Cthulhuphant
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1444] => Array
                        (
                            [name] => Hero_Tremble.main_reskin
                            [cname] => Iron Tremble
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1446] => Array
                        (
                            [name] => Hero_Chipper.Alt2
                            [cname] => Chiprel Strike Squad
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1448] => Array
                        (
                            [name] => Hero_Mumra.Alt3
                            [cname] => Anubis Pharaoh
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1450] => Array
                        (
                            [name] => Hero_Panda.Alt2
                            [cname] => Muay Tigermonium
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1452] => Array
                        (
                            [name] => Hero_Maliken.Alt2
                            [cname] => Young Maliken
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1454] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt2
                            [cname] => Drunken Wench
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1456] => Array
                        (
                            [name] => Hero_Rampage.Alt4
                            [cname] => Primal Rampage
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1461] => Array
                        (
                            [name] => Hero_Lodestone.Alt
                            [cname] => Shrapnel
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1464] => Array
                        (
                            [name] => Hero_Lodestone.Alt2
                            [cname] => Heap
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1467] => Array
                        (
                            [name] => Hero_Shaman.Alt2
                            [cname] => Demonic Shaman
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1469] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt3
                            [cname] => Pra Ram Archer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1471] => Array
                        (
                            [name] => Hero_Ellonia.Alt2
                            [cname] => Jackson Frost
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1473] => Array
                        (
                            [name] => Hero_Rampage.Alt5
                            [cname] => Rudy Rampage
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1475] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt3
                            [cname] => Eggnog Master
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1477] => Array
                        (
                            [name] => Hero_Frosty.Alt3
                            [cname] => Frosty the Iceman
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1479] => Array
                        (
                            [name] => Hero_Krixi.Alt2
                            [cname] => Moon Prince
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1481] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt3
                            [cname] => Bravehurt Hammerstorm
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1483] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt3
                            [cname] => Arcsara Puppetmaster
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1486] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt5
                            [cname] => Flint Hellwood
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1488] => Array
                        (
                            [name] => Hero_Treant.Alt3
                            [cname] => Keeper of the Desert
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1490] => Array
                        (
                            [name] => Hero_Vanya.Alt_reskin
                            [cname] => Glorious Dark Lady
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1494] => Array
                        (
                            [name] => Hero_Rhapsody.Alt2
                            [cname] => DJ Rap City
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1496] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt4
                            [cname] => Topiary Warden
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1504] => Array
                        (
                            [name] => Hero_HellDemon.Alt2
                            [cname] => Charon 
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1505] => Array
                        (
                            [name] => Hero_Yogi.Alt2
                            [cname] => Dr. Beebo and Loofy
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1506] => Array
                        (
                            [name] => Hero_Parasite.Alt3
                            [cname] => Facehugger
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1510] => Array
                        (
                            [name] => Hero_Bombardier.Alt3
                            [cname] => Turtlepult
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1512] => Array
                        (
                            [name] => Hero_Rally.Alt3
                            [cname] => Tyrant
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1514] => Array
                        (
                            [name] => Hero_Armadon.Alt3
                            [cname] => Vagabonadon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1520] => Array
                        (
                            [name] => Hero_Chronos.Alt3
                            [cname] => Time Lord Chronos
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1524] => Array
                        (
                            [name] => Hero_Bushwack.Alt
                            [cname] => Harcoon
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1527] => Array
                        (
                            [name] => Hero_Bushwack.Alt2
                            [cname] => Ven
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1530] => Array
                        (
                            [name] => Hero_Hunter.Alt3
                            [cname] => Stealth Hunter
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1540] => Array
                        (
                            [name] => Hero_Silhouette.Alt3
                            [cname] => Sileena
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1542] => Array
                        (
                            [name] => Hero_Pearl.Alt3
                            [cname] => Ruby
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1546] => Array
                        (
                            [name] => Hero_Scout.Alt3
                            [cname] => RXR9 the Cyber Scout
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1548] => Array
                        (
                            [name] => Hero_Blitz.Alt2
                            [cname] => Quarterback Blitz
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1550] => Array
                        (
                            [name] => Hero_Tremble.Alt2
                            [cname] => Groundhog Tremble
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1552] => Array
                        (
                            [name] => Hero_SandWraith.Alt2
                            [cname] => Shadow Wraith
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1556] => Array
                        (
                            [name] => Hero_WolfMan.Alt2
                            [cname] => Den Mother
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1559] => Array
                        (
                            [name] => Hero_Accursed.Alt2
                            [cname] => Diseased Accursed
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1561] => Array
                        (
                            [name] => Hero_Revenant.Alt2
                            [cname] => Savage Revenant
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1563] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt3
                            [cname] => Hope
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1565] => Array
                        (
                            [name] => Hero_Kunas.Alt3
                            [cname] => Lightningbringer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1570] => Array
                        (
                            [name] => Hero_Tundra.Alt3
                            [cname] => Odin
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1572] => Array
                        (
                            [name] => Hero_Ravenor.Alt3
                            [cname] => Zeus
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1574] => Array
                        (
                            [name] => Hero_Magmar.Alt3
                            [cname] => Svarog
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1582] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt2
                            [cname] => Shadowbeast
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1584] => Array
                        (
                            [name] => Hero_Oogie.Alt3
                            [cname] => Mardi Gras Oogie
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1585] => Array
                        (
                            [name] => Hero_Xalynx.Alt3
                            [cname] => Celsius
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1589] => Array
                        (
                            [name] => Hero_Salomon.Alt
                            [cname] => Tengshe
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1590] => Array
                        (
                            [name] => Hero_Salomon.Alt2
                            [cname] => Sharac
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1596] => Array
                        (
                            [name] => Hero_Solstice.Alt4
                            [cname] => Guan Yu
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1598] => Array
                        (
                            [name] => Hero_Grinex.Alt3
                            [cname] => SlenderX
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1600] => Array
                        (
                            [name] => Hero_Berzerker.Alt3
                            [cname] => Gutbuster
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1602] => Array
                        (
                            [name] => Hero_Zephyr.Alt4
                            [cname] => Quetzalcoatl
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1604] => Array
                        (
                            [name] => Hero_Defiler.Alt2
                            [cname] => Kali the Destroyer
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1606] => Array
                        (
                            [name] => Hero_Moraxus.Alt2
                            [cname] => Morockus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1608] => Array
                        (
                            [name] => Hero_Dampeer.Alt3
                            [cname] => Duchess Dampeer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1610] => Array
                        (
                            [name] => Hero_Hydromancer.Alt3
                            [cname] => Walradon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1614] => Array
                        (
                            [name] => Hero_Plant.Alt2
                            [cname] => Fungal Bramble
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1616] => Array
                        (
                            [name] => Hero_Deadwood.Alt3
                            [cname] => Toadwood Deadstool
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1620] => Array
                        (
                            [name] => Hero_Valkyrie.Classic
                            [cname] => Throwback Valkyrie
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1621] => Array
                        (
                            [name] => Hero_Krixi.Classic
                            [cname] => Throwback Moon Queen
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1622] => Array
                        (
                            [name] => Hero_Accursed.Classic
                            [cname] => Throwback Accursed
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1623] => Array
                        (
                            [name] => Hero_Hunter.Classic
                            [cname] => Throwback Blood Hunter
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1624] => Array
                        (
                            [name] => Hero_PuppetMaster.Classic
                            [cname] => Throwback Puppet Master
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1625] => Array
                        (
                            [name] => Hero_Hiro.Classic
                            [cname] => Throwback Swiftblade
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1626] => Array
                        (
                            [name] => Hero_SandWraith.Classic
                            [cname] => Throwback Sand Wraith
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1627] => Array
                        (
                            [name] => Hero_Yogi.Classic
                            [cname] => Throwback Wildsoul
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1628] => Array
                        (
                            [name] => Hero_WolfMan.Classic
                            [cname] => Throwback War Beast
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1630] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt2
                            [cname] => Leper
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1632] => Array
                        (
                            [name] => Hero_Legionnaire.Alt4
                            [cname] => Quintan
                            [cost] => 780
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1634] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt3
                            [cname] => Dyad
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1636] => Array
                        (
                            [name] => Hero_Engineer.Alt3
                            [cname] => Troika
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1638] => Array
                        (
                            [name] => Hero_Scout.Alt4
                            [cname] => Tetra
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1640] => Array
                        (
                            [name] => Hero_Martyr.Alt2
                            [cname] => Unum
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1642] => Array
                        (
                            [name] => Hero_Kraken.Alt3
                            [cname] => Gnarwhal
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1644] => Array
                        (
                            [name] => Hero_Devourer.Alt5
                            [cname] => Jin Chan
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1648] => Array
                        (
                            [name] => Hero_Kunas.Alt2
                            [cname] => Syrrus the Lightning Caller
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1650] => Array
                        (
                            [name] => Hero_Arachna.main_reskin
                            [cname] => Arachnabot
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1652] => Array
                        (
                            [name] => Hero_Monarch.Alt3
                            [cname] => Tera Monarch
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1654] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt4
                            [cname] => Hammer Lord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1656] => Array
                        (
                            [name] => Hero_Fairy.Alt2
                            [cname] => Fat Nymphora
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1658] => Array
                        (
                            [name] => Hero_Devourer.Alt6
                            [cname] => Rift Devourer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1682] => Array
                        (
                            [name] => Hero_Gauntlet.Alt3
                            [cname] => Siege Gauntlet
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1660] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt6
                            [cname] => Tommy TwoGun
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1662] => Array
                        (
                            [name] => Hero_Predator.Alt4
                            [cname] => Rift Predator
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1664] => Array
                        (
                            [name] => Hero_Tempest.Alt2
                            [cname] => Deconstructor
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1666] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt4
                            [cname] => Penguin Priest
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1668] => Array
                        (
                            [name] => Hero_Gemini.Alt3
                            [cname] => Fu Lion Gemini
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1670] => Array
                        (
                            [name] => Hero_Prisoner.Alt
                            [cname] => Baaracko
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1672] => Array
                        (
                            [name] => Hero_Prisoner.Alt2
                            [cname] => Brutavious
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1686] => Array
                        (
                            [name] => Hero_Zephyr.Alt5
                            [cname] => Party Zephyr
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1688] => Array
                        (
                            [name] => Hero_Arachna.Alt3
                            [cname] => Rift Arachna
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1690] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt4
                            [cname] => Tequila Master
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1692] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt7
                            [cname] => Smuggler Flint
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1694] => Array
                        (
                            [name] => Hero_Hellbringer.Alt3
                            [cname] => Elementbringer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1698] => Array
                        (
                            [name] => Hero_SirBenzington.Alt
                            [cname] => Sir Terrowin
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1700] => Array
                        (
                            [name] => Hero_SirBenzington.Alt2
                            [cname] => Sir Benzalot
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1705] => Array
                        (
                            [name] => Hero_Andromeda.Classic
                            [cname] => Throwback Andromeda
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1706] => Array
                        (
                            [name] => Hero_Deadwood.Classic
                            [cname] => Throwback Deadwood
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1707] => Array
                        (
                            [name] => Hero_Defiler.Classic
                            [cname] => Throwback Defiler
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1708] => Array
                        (
                            [name] => Hero_Devourer.Classic
                            [cname] => Throwback Devourer
                            [cost] => 1
                            [premium] => 0
                            [premium_mmp_cost] => 1
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1709] => Array
                        (
                            [name] => Hero_Frosty.Classic
                            [cname] => Throwback Glacius
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1710] => Array
                        (
                            [name] => Hero_Treant.Classic
                            [cname] => Throwback Keeper of the Forest
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1711] => Array
                        (
                            [name] => Hero_Legionnaire.Classic
                            [cname] => Throwback Legionnaire
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1712] => Array
                        (
                            [name] => Hero_Scar.Classic
                            [cname] => Throwback Madman
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1713] => Array
                        (
                            [name] => Hero_Javaras.Classic
                            [cname] => Throwback Magebane
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1714] => Array
                        (
                            [name] => Hero_Martyr.Classic
                            [cname] => Throwback Martyr
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1715] => Array
                        (
                            [name] => Hero_Hantumon.Classic
                            [cname] => Throwback Night Hound
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1716] => Array
                        (
                            [name] => Hero_Ophelia.Classic
                            [cname] => Throwback Ophelia
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1717] => Array
                        (
                            [name] => Hero_Rocky.Classic
                            [cname] => Throwback Pebbles
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1718] => Array
                        (
                            [name] => Hero_Mumra.Classic
                            [cname] => Throwback Pharaoh
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1719] => Array
                        (
                            [name] => Hero_Scout.Classic
                            [cname] => Throwback Scout
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1720] => Array
                        (
                            [name] => Hero_Ebulus.Classic
                            [cname] => Throwback Slither
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1721] => Array
                        (
                            [name] => Hero_Soulstealer.Classic
                            [cname] => Throwback Soulstealer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1722] => Array
                        (
                            [name] => Hero_Succubis.Classic
                            [cname] => Throwback Succubus
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1723] => Array
                        (
                            [name] => Hero_Tempest.Classic
                            [cname] => Throwback Tempest
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1724] => Array
                        (
                            [name] => Hero_Vanya.Classic
                            [cname] => Throwback Dark Lady
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1725] => Array
                        (
                            [name] => Hero_Xalynx.Classic
                            [cname] => Throwback Torturer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1737] => Array
                        (
                            [name] => Hero_Legionnaire.Alt5
                            [cname] => Chip Legionnaire
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1739] => Array
                        (
                            [name] => Hero_Berzerker.Alt4
                            [cname] => Dale Berzerker
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1741] => Array
                        (
                            [name] => Hero_Nomad.Alt4
                            [cname] => Elly Nomad
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1743] => Array
                        (
                            [name] => Hero_Prophet.Alt3
                            [cname] => Lord Garuda
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1745] => Array
                        (
                            [name] => Hero_Valkyrie.Alt5
                            [cname] => Impaler Valk
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1747] => Array
                        (
                            [name] => Hero_Jereziah.Alt3
                            [cname] => Inti Jeraziah
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1749] => Array
                        (
                            [name] => Hero_Gladiator.Alt4
                            [cname] => Matador Gladiator
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1757] => Array
                        (
                            [name] => Hero_Rampage.Alt6
                            [cname] => Hunter Rampage
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1759] => Array
                        (
                            [name] => Hero_Hiro.Alt5
                            [cname] => Hunter Swiftblade
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1761] => Array
                        (
                            [name] => Hero_Bushwack.Alt3
                            [cname] => Hunter Bushwack
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1763] => Array
                        (
                            [name] => Hero_Bubbles.Alt4
                            [cname] => Rift Bubbles
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1765] => Array
                        (
                            [name] => Hero_Rally.Alt4
                            [cname] => Hunter Rally
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1767] => Array
                        (
                            [name] => Hero_Ebulus.Alt3
                            [cname] => Rift Slither
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1769] => Array
                        (
                            [name] => Hero_Gunblade.Alt3
                            [cname] => Hunter Gunblade
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1771] => Array
                        (
                            [name] => Hero_Riftmage.Alt2
                            [cname] => Queen Riftwalker
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1773] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt5
                            [cname] => Rift Warden
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1775] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt4
                            [cname] => Hunter Witch Slayer
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1777] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt4
                            [cname] => Sun Wukong
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1779] => Array
                        (
                            [name] => Hero_FlameDragon.Alt3
                            [cname] => Primal Dracon
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1781] => Array
                        (
                            [name] => Hero_Revenant.Alt3
                            [cname] => Ruin Revenant
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1783] => Array
                        (
                            [name] => Hero_Yogi.Alt3
                            [cname] => Pandasoul
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1794] => Array
                        (
                            [name] => Hero_Maliken.Alt4
                            [cname] => Slasher Maliken
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1798] => Array
                        (
                            [name] => Hero_Bubbles.pog_skin
                            [cname] => POG Bubbles
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1815] => Array
                        (
                            [name] => Hero_HellDemon.Alt3
                            [cname] => Yanluo Wang
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1825] => Array
                        (
                            [name] => Hero_Martyr.Alt3
                            [cname] => Tangseng
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1827] => Array
                        (
                            [name] => Hero_Prisoner.Alt3
                            [cname] => Bajie
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1829] => Array
                        (
                            [name] => Hero_Javaras.Alt3
                            [cname] => Shaolin Magebane
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1831] => Array
                        (
                            [name] => Hero_Panda.Alt3
                            [cname] => Jeet Kune Dragon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1833] => Array
                        (
                            [name] => Hero_Pyromancer.Alt4
                            [cname] => Steampunk Pyromancer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1835] => Array
                        (
                            [name] => Hero_Geomancer.Alt3
                            [cname] => Drillex
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1837] => Array
                        (
                            [name] => Hero_Moraxus.Alt3
                            [cname] => Mortracksus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1839] => Array
                        (
                            [name] => Hero_Hunter.Alt4
                            [cname] => Organ Grinder Bloodhunter
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1841] => Array
                        (
                            [name] => Hero_Behemoth.Alt3
                            [cname] => Steamoth
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1843] => Array
                        (
                            [name] => Hero_Aluna.Alt3
                            [cname] => Steampunk Aluna
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1845] => Array
                        (
                            [name] => Hero_Predator.Alt5
                            [cname] => Nightmare Predator
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1847] => Array
                        (
                            [name] => Hero_SandWraith.Alt3
                            [cname] => Hang Tuah
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1849] => Array
                        (
                            [name] => Hero_Hydromancer.Alt4
                            [cname] => Sea King Myrmidon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1907] => Array
                        (
                            [name] => Hero_Ophelia.Alt3
                            [cname] => Sylvia
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1962] => Array
                        (
                            [name] => Hero_Gemini.Alt4
                            [cname] => Cerberus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1878] => Array
                        (
                            [name] => Hero_BabaYaga.Alt3
                            [cname] => Wicked Hag of the West
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1876] => Array
                        (
                            [name] => Hero_Devourer.Alt7
                            [cname] => Captain Gorebeard
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1880] => Array
                        (
                            [name] => Hero_Empath.Alt3
                            [cname] => Guanyin
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1882] => Array
                        (
                            [name] => Hero_Aluna.Alt2
                            [cname] => Conquistador Aluna
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1884] => Array
                        (
                            [name] => Hero_Salomon.Alt3
                            [cname] => Djinn Salomon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1886] => Array
                        (
                            [name] => Hero_Pestilence.Alt4
                            [cname] => Swarm Pestilence
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1888] => Array
                        (
                            [name] => Hero_Ravenor.Alt4
                            [cname] => Rift Ravenor
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1890] => Array
                        (
                            [name] => Hero_Chronos.Alt4
                            [cname] => Ghatotkacha
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1892] => Array
                        (
                            [name] => Hero_Dreadknight.Alt4
                            [cname] => Baron of Blackwal
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1894] => Array
                        (
                            [name] => Hero_Artillery.Alt3
                            [cname] => Gorilla Warfare Artillery
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1896] => Array
                        (
                            [name] => Hero_Blitz.Alt3
                            [cname] => Flash Blitz
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1909] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt5
                            [cname] => TDMonkey King
                            [cost] => 100
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1911] => Array
                        (
                            [name] => Hero_Taint.Alt3
                            [cname] => Snot Keeper
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1913] => Array
                        (
                            [name] => Hero_Rocky.Alt4
                            [cname] => Earthroc Pebbles
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1915] => Array
                        (
                            [name] => Hero_Gunblade.Alt4
                            [cname] => Cossack
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1917] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt4
                            [cname] => Ogre Blacksmith
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1919] => Array
                        (
                            [name] => Hero_Treant.Alt4
                            [cname] => Willow Keeper
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1921] => Array
                        (
                            [name] => Hero_Hantumon.Alt4
                            [cname] => Cowardly Night Hound
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1923] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt3
                            [cname] => Robotron
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1925] => Array
                        (
                            [name] => Hero_Fade.Alt2
                            [cname] => Scarecrow Fayde
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1927] => Array
                        (
                            [name] => Hero_Deadwood.Alt4
                            [cname] => Gravewood Deadyard
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1929] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt5
                            [cname] => Tin Hammerstorm
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1931] => Array
                        (
                            [name] => Hero_Pearl.Alt4
                            [cname] => Good Witch Pearl
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1934] => Array
                        (
                            [name] => Hero_Ravenor.Alt5
                            [cname] => El Diablo
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1936] => Array
                        (
                            [name] => Hero_Soulstealer.Alt3
                            [cname] => Hades
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1938] => Array
                        (
                            [name] => Hero_Vanya.Alt3
                            [cname] => Set
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1940] => Array
                        (
                            [name] => Hero_Ellonia.Alt3
                            [cname] => Ymir
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1942] => Array
                        (
                            [name] => Hero_Dampeer.Alt4
                            [cname] => Camazotz
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1944] => Array
                        (
                            [name] => Hero_Voodoo.Alt3
                            [cname] => Hel
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1946] => Array
                        (
                            [name] => Hero_Bubbles.Alt5
                            [cname] => Cosmonaut Bubbles
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1948] => Array
                        (
                            [name] => Hero_Andromeda.Alt3
                            [cname] => Gundromeda
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1950] => Array
                        (
                            [name] => Hero_Lodestone.Alt3
                            [cname] => Penitent Lodestone
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1952] => Array
                        (
                            [name] => Hero_Krixi.Alt3
                            [cname] => Eclipse 
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1954] => Array
                        (
                            [name] => Hero_FlameDragon.Alt4
                            [cname] => Mecha Draconis
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1956] => Array
                        (
                            [name] => Hero_Grinex.Alt4
                            [cname] => Cyber Steel Grinex
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1958] => Array
                        (
                            [name] => Hero_Pyromancer.Alt5
                            [cname] => Brimstone
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1960] => Array
                        (
                            [name] => Hero_BabaYaga.Alt4
                            [cname] => Baba Yaga
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1964] => Array
                        (
                            [name] => Hero_Defiler.Alt3
                            [cname] => La Llorona
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1966] => Array
                        (
                            [name] => Hero_Gauntlet.Alt4
                            [cname] => Grendel
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1968] => Array
                        (
                            [name] => Hero_Scar.Alt3
                            [cname] => Chupacabra
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1970] => Array
                        (
                            [name] => Hero_Rampage.Alt9
                            [cname] => Wyvern Rampage
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1972] => Array
                        (
                            [name] => Hero_Rally.Alt5
                            [cname] => Bogatyr
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1974] => Array
                        (
                            [name] => Hero_Accursed.Alt3
                            [cname] => Green Knight
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1976] => Array
                        (
                            [name] => Hero_Vindicator.Alt3
                            [cname] => Merlin
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1978] => Array
                        (
                            [name] => Hero_Artesia.Alt3
                            [cname] => Artesia le Fay
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1980] => Array
                        (
                            [name] => Hero_Legionnaire.Alt6
                            [cname] => The Kurgan
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1995] => Array
                        (
                            [name] => Hero_Circe.Alt
                            [cname] => Iron Maiden
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1997] => Array
                        (
                            [name] => Hero_Circe.Alt2
                            [cname] => Poison Circe
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2002] => Array
                        (
                            [name] => Hero_HellDemon.Alt4
                            [cname] => RoboReaper
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2004] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt4
                            [cname] => Master of Cybernetics
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2006] => Array
                        (
                            [name] => Hero_Ebulus.Alt4
                            [cname] => Sally Slither
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2008] => Array
                        (
                            [name] => Hero_Plant.Alt3
                            [cname] => Bobbi Bramble
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2010] => Array
                        (
                            [name] => Hero_Panda.Alt4
                            [cname] => Amanda Panda
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2012] => Array
                        (
                            [name] => Hero_Behemoth.Alt4
                            [cname] => Basher Behemoth
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2014] => Array
                        (
                            [name] => Hero_Prophet.Alt4
                            [cname] => The Blind Prophet
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2018] => Array
                        (
                            [name] => Hero_Silhouette.Alt4
                            [cname] => Arbinger
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2020] => Array
                        (
                            [name] => Hero_Berzerker.Alt5
                            [cname] => Orbode
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2022] => Array
                        (
                            [name] => Hero_Jereziah.Alt4
                            [cname] => Omen
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2024] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt3
                            [cname] => Edium
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2026] => Array
                        (
                            [name] => Hero_Kenisis.Alt3
                            [cname] => Augur
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2032] => Array
                        (
                            [name] => Hero_Ra.Alt4
                            [cname] => RoboRa
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2034] => Array
                        (
                            [name] => Hero_Nomad.Alt5
                            [cname] => Diligence
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2036] => Array
                        (
                            [name] => Hero_Parasite.Alt4
                            [cname] => NanoParasite
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2038] => Array
                        (
                            [name] => Hero_Armadon.Alt4
                            [cname] => Robodon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2040] => Array
                        (
                            [name] => Hero_Succubis.Alt3
                            [cname] => Chastity
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2042] => Array
                        (
                            [name] => Hero_Midas.Alt4
                            [cname] => Charity
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2044] => Array
                        (
                            [name] => Hero_Chronos.Alt5
                            [cname] => Patience
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2046] => Array
                        (
                            [name] => Hero_Xalynx.Alt4
                            [cname] => Kindness
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2048] => Array
                        (
                            [name] => Hero_Prisoner.Alt4
                            [cname] => Temperance
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2050] => Array
                        (
                            [name] => Hero_Nomad.Alt6
                            [cname] => Exterminator Nomad
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2052] => Array
                        (
                            [name] => Hero_Maliken.Alt5
                            [cname] => Humility
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2071] => Array
                        (
                            [name] => Hero_Engineer.Alt4
                            [cname] => Tork
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2073] => Array
                        (
                            [name] => Hero_Bephelgor.Alt4
                            [cname] => Baker Balphagore
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2075] => Array
                        (
                            [name] => Hero_Shaman.Alt3
                            [cname] => Lollipop Shaman
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2077] => Array
                        (
                            [name] => Hero_Bombardier.Alt4
                            [cname] => Ice Cream Bombardier
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2079] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt3
                            [cname] => Candy Rider
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2081] => Array
                        (
                            [name] => Hero_Aluna.Alt4
                            [cname] => Santa Baby Aluna
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2083] => Array
                        (
                            [name] => Hero_Solstice.Alt5
                            [cname] => Winter Solstice
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2085] => Array
                        (
                            [name] => Hero_Magmar.Alt4
                            [cname] => Cryo Magmus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2087] => Array
                        (
                            [name] => Hero_Flux.Alt3
                            [cname] => Jupiter
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2089] => Array
                        (
                            [name] => Hero_Artillery.Alt4
                            [cname] => Apollo
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2091] => Array
                        (
                            [name] => Hero_Tempest.Alt3
                            [cname] => Poseidon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2093] => Array
                        (
                            [name] => Hero_SirBenzington.Alt3
                            [cname] => Sir Lancelot
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2095] => Array
                        (
                            [name] => Hero_Geomancer.Alt4
                            [cname] => Basilisk
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2097] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt5
                            [cname] => Dionysus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2099] => Array
                        (
                            [name] => Hero_Scout.Alt5
                            [cname] => Hermes
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2101] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt4
                            [cname] => Loki
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2103] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt4
                            [cname] => Anunnaki
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2105] => Array
                        (
                            [name] => Hero_Nomad.Alt7
                            [cname] => Eskinomad
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2111] => Array
                        (
                            [name] => Hero_Klanx.Alt
                            [cname] => Sky Pirate Klanx
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2113] => Array
                        (
                            [name] => Hero_Klanx.Alt2
                            [cname] => Doomsday Klanx
                            [cost] => 780
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2120] => Array
                        (
                            [name] => Hero_Accursed.pog_skin
                            [cname] => POG Accursed
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2122] => Array
                        (
                            [name] => Hero_Andromeda.pog_skin
                            [cname] => POG Andromeda
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2124] => Array
                        (
                            [name] => Hero_Electrician.pog_skin
                            [cname] => POG Electrician
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2125] => Array
                        (
                            [name] => Hero_Arachna.pog_skin
                            [cname] => POG Arachna
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2126] => Array
                        (
                            [name] => Hero_Armadon.pog_skin
                            [cname] => POG Armadon
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2128] => Array
                        (
                            [name] => Hero_Behemoth.pog_skin
                            [cname] => POG Behemoth
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2130] => Array
                        (
                            [name] => Hero_Bephelgor.pog_skin
                            [cname] => POG Balphagore
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2132] => Array
                        (
                            [name] => Hero_DwarfMagi.pog_skin
                            [cname] => POG Blacksmith
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2134] => Array
                        (
                            [name] => Hero_Hunter.pog_skin
                            [cname] => POG Blood Hunter
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2136] => Array
                        (
                            [name] => Hero_Chipper.pog_skin
                            [cname] => POG Chipper
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2171] => Array
                        (
                            [name] => Hero_Rally.Alt6
                            [cname] => Yeniceri
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2173] => Array
                        (
                            [name] => Hero_Electrician.Alt3
                            [cname] => Osiris
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2175] => Array
                        (
                            [name] => Hero_FlameDragon.Alt5
                            [cname] => Sphinx
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2177] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt4
                            [cname] => Pegasus
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2180] => Array
                        (
                            [name] => Hero_Hiro.Alt6
                            [cname] => Halion
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2182] => Array
                        (
                            [name] => Hero_Kunas.Alt6
                            [cname] => Asgard Thor
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2184] => Array
                        (
                            [name] => Hero_Gunblade.Alt5
                            [cname] => Tyr
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2186] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt6
                            [cname] => Hercules
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2188] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt6
                            [cname] => Dionysus Mead Viking
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2190] => Array
                        (
                            [name] => Hero_Javaras.Alt4
                            [cname] => Syphon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2192] => Array
                        (
                            [name] => Hero_Circe.Alt3
                            [cname] => Veil
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2194] => Array
                        (
                            [name] => Hero_Rhapsody.Alt3
                            [cname] => Rhapscallion
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2196] => Array
                        (
                            [name] => Hero_Gladiator.Alt5
                            [cname] => Halcyon Judicator
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2198] => Array
                        (
                            [name] => Hero_Fade.Alt3
                            [cname] => Vanish
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2200] => Array
                        (
                            [name] => Hero_Zephyr.Alt6
                            [cname] => Horus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2202] => Array
                        (
                            [name] => Hero_Taint.Alt4
                            [cname] => Hestia
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2217] => Array
                        (
                            [name] => Hero_Tundra.Alt4
                            [cname] => Allfather Odin
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2221] => Array
                        (
                            [name] => Hero_Moira.Alt2
                            [cname] => Singularity
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2223] => Array
                        (
                            [name] => Hero_Moira.Alt
                            [cname] => Hecate
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2225] => Array
                        (
                            [name] => Hero_Midas.Alt5
                            [cname] => Coral Snake Medusa
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2227] => Array
                        (
                            [name] => Hero_Ellonia.Alt4
                            [cname] => Cursed Woodpuppet Ymir
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2229] => Array
                        (
                            [name] => Hero_Defiler.Alt4
                            [cname] => Chaos Realm Kali
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2231] => Array
                        (
                            [name] => Hero_Hellbringer.Alt4
                            [cname] => Jade Empress
                            [cost] => 9004
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2233] => Array
                        (
                            [name] => Hero_SirBenzington.Alt5
                            [cname] => Drop Bearzington
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2243] => Array
                        (
                            [name] => Hero_Fairy.Alt3
                            [cname] => Luckphora
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2245] => Array
                        (
                            [name] => Hero_Hantumon.pog_skin
                            [cname] => POG Night Hound
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2246] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt7
                            [cname] => Rum Master
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2250] => Array
                        (
                            [name] => Hero_Voodoo.Alt4
                            [cname] => Ragnarok Hel
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2252] => Array
                        (
                            [name] => Hero_Shaman.Alt4
                            [cname] => Battle Armor Athena
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2254] => Array
                        (
                            [name] => Hero_Legionnaire.Alt7
                            [cname] => Boudica
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2256] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt8
                            [cname] => Flinty Widowmaker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2258] => Array
                        (
                            [name] => Hero_Ra.Alt5
                            [cname] => Acolyte
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2260] => Array
                        (
                            [name] => Hero_Succubis.pog_skin
                            [cname] => POG Succubus
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2261] => Array
                        (
                            [name] => Hero_Scout.Alt6
                            [cname] => Scoutzo the Clown
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2265] => Array
                        (
                            [name] => Hero_Riptide.Alt
                            [cname] => Toxin
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2267] => Array
                        (
                            [name] => Hero_Riptide.Alt2
                            [cname] => Pisces
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2269] => Array
                        (
                            [name] => Hero_Riptide.Alt3
                            [cname] => War Blossom
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2271] => Array
                        (
                            [name] => Hero_Hunter.Alt5
                            [cname] => Gargoyle
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2275] => Array
                        (
                            [name] => Hero_SandWraith.Alt4
                            [cname] => Blight Wraith
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2277] => Array
                        (
                            [name] => Hero_Frosty.Alt4
                            [cname] => Nuclear Winter Glacius
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2279] => Array
                        (
                            [name] => Hero_Klanx.Alt3
                            [cname] => Safari Klanx
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2281] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt5
                            [cname] => Master of Songkran
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2283] => Array
                        (
                            [name] => Hero_Rampage.Alt7
                            [cname] => Songkran Rampage
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2285] => Array
                        (
                            [name] => Hero_Rampage.Alt8
                            [cname] => Road Rage Rampage
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2287] => Array
                        (
                            [name] => Hero_Hantumon.Alt5
                            [cname] => Rabid Night Bunny
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2289] => Array
                        (
                            [name] => Hero_Treant.Alt5
                            [cname] => Keeper of the Green
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2291] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt5
                            [cname] => Axolotl Pollywog
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2293] => Array
                        (
                            [name] => Hero_Chipper.Alt3
                            [cname] => Arctic Harrier
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2295] => Array
                        (
                            [name] => Hero_Tremble.Alt3
                            [cname] => King Crab Tremble
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2297] => Array
                        (
                            [name] => Hero_Armadon.Alt5
                            [cname] => Horny Lizardon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2299] => Array
                        (
                            [name] => Hero_Empath.Alt4
                            [cname] => Gaia
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2301] => Array
                        (
                            [name] => Hero_Panda.Alt5
                            [cname] => Hippomonium
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2303] => Array
                        (
                            [name] => Hero_Hiro.Alt7
                            [cname] => Cyber Samurai
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2305] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt4
                            [cname] => Effigy
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2307] => Array
                        (
                            [name] => Hero_Artesia.Alt4
                            [cname] => Corsair
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2320] => Array
                        (
                            [name] => Hero_Fairy.pog_skin
                            [cname] => POG Nymphora
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2321] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt4
                            [cname] => Caller Cthulhuphant
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2323] => Array
                        (
                            [name] => Hero_Fade.pog_skin
                            [cname] => POG Fayde
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2324] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt5
                            [cname] => Partisan Slayer
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2326] => Array
                        (
                            [name] => Hero_Jereziah.Alt5
                            [cname] => Liberator
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2328] => Array
                        (
                            [name] => Hero_Monarch.Alt4
                            [cname] => Cherub
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2330] => Array
                        (
                            [name] => Hero_Krixi.pog_skin
                            [cname] => POG Moon Queen
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2331] => Array
                        (
                            [name] => Hero_Shaman.Alt5
                            [cname] => Goddess Armor Athena
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2333] => Array
                        (
                            [name] => Hero_Zephyr.Alt7
                            [cname] => Parrot
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2335] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt3
                            [cname] => Husher
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2337] => Array
                        (
                            [name] => Hero_Devourer.Alt8
                            [cname] => Kodia
                            [cost] => 450
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2340] => Array
                        (
                            [name] => Hero_Hellbringer.Alt5
                            [cname] => Imperial Summoner
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2342] => Array
                        (
                            [name] => Hero_Electrician.Alt4
                            [cname] => Royal Armor Osiris
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2344] => Array
                        (
                            [name] => Hero_CorruptedDisciple.pog_skin
                            [cname] => POG Corrupted Disciple
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2357] => Array
                        (
                            [name] => Hero_Vindicator.Alt5
                            [cname] => Sexy Librarian
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2359] => Array
                        (
                            [name] => Hero_Predator.Alt6
                            [cname] => Russian Battlebear
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2362] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt5
                            [cname] => Battle Armor Pegasus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2364] => Array
                        (
                            [name] => Hero_Bubbles.Alt7
                            [cname] => Venus De Bubbles
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2366] => Array
                        (
                            [name] => Hero_FlintBeastwood.pog_skin
                            [cname] => POG Flint Beastwood
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2367] => Array
                        (
                            [name] => Hero_WolfMan.Alt3
                            [cname] => Shock Troop War
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2369] => Array
                        (
                            [name] => Hero_ForsakenArcher.pog_skin
                            [cname] => POG Forsaken Archer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2370] => Array
                        (
                            [name] => Hero_WitchSlayer.pog_skin
                            [cname] => POG Witch Slayer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2371] => Array
                        (
                            [name] => Hero_Soulstealer.Alt4
                            [cname] => Redeemed Hades
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2373] => Array
                        (
                            [name] => Hero_Artillery.Alt5
                            [cname] => Rock God Apollo
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2375] => Array
                        (
                            [name] => Hero_Tempest.Alt4
                            [cname] => Shark Hunter Poseidon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2377] => Array
                        (
                            [name] => Hero_Chronos.Alt6
                            [cname] => Savage Mace Chronos
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2381] => Array
                        (
                            [name] => Hero_Tarot.Alt
                            [cname] => Icosa
                            [cost] => 9001
                            [premium] => 1
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2383] => Array
                        (
                            [name] => Hero_Tarot.Alt2
                            [cname] => Tyche
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2385] => Array
                        (
                            [name] => Hero_Tarot.Alt3
                            [cname] => Roulette
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2387] => Array
                        (
                            [name] => Hero_Martyr.Alt4
                            [cname] => Sister Death
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2389] => Array
                        (
                            [name] => Hero_Zephyr.pog_skin
                            [cname] => POG Zephyr
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2390] => Array
                        (
                            [name] => Hero_Hunter.Alt6
                            [cname] => Balrog
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2392] => Array
                        (
                            [name] => Hero_Geomancer.Alt5
                            [cname] => Chameleon Basilisk
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2394] => Array
                        (
                            [name] => Hero_Taint.Alt5
                            [cname] => Wave Queen Hestia
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2396] => Array
                        (
                            [name] => Hero_Prisoner.Alt5
                            [cname] => Dark Angel
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2398] => Array
                        (
                            [name] => Hero_Devourer.pog_skin
                            [cname] => POG Devourer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2399] => Array
                        (
                            [name] => Hero_Monarch.Alt5
                            [cname] => Luna Moth Cherub
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2401] => Array
                        (
                            [name] => Hero_Mumra.pog_skin
                            [cname] => POG Pharaoh
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2402] => Array
                        (
                            [name] => Hero_WolfMan.Alt4
                            [cname] => Skullcrusher
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2404] => Array
                        (
                            [name] => Hero_Magmar.Alt5
                            [cname] => Taurus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2406] => Array
                        (
                            [name] => Hero_Pearl.Alt5
                            [cname] => Malice
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2408] => Array
                        (
                            [name] => Hero_Plant.Alt4
                            [cname] => Manticore
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2410] => Array
                        (
                            [name] => Hero_Berzerker.Alt6
                            [cname] => Insanitarius Berzerker
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2412] => Array
                        (
                            [name] => Hero_FlameDragon.Alt6
                            [cname] => Gryphon Draconis
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2414] => Array
                        (
                            [name] => Hero_Salomon.Alt4
                            [cname] => Wicked Wish
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2416] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt4
                            [cname] => Sinew
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2418] => Array
                        (
                            [name] => Hero_SirBenzington.Alt4
                            [cname] => End Bringer Lancelot
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2420] => Array
                        (
                            [name] => Hero_Vindicator.Alt6
                            [cname] => Space Wizard Merlin
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2422] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt6
                            [cname] => Olympic Pegasus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2424] => Array
                        (
                            [name] => Hero_Bubbles.Alt6
                            [cname] => Aquarius
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2426] => Array
                        (
                            [name] => Hero_Klanx.Alt4
                            [cname] => Winter Soldier Klanx
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2429] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt9
                            [cname] => Rulian Warlord Flint
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2431] => Array
                        (
                            [name] => Hero_Prophet.Alt5
                            [cname] => Dynasty
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2438] => Array
                        (
                            [name] => Hero_Moraxus.Alt4
                            [cname] => Axia
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2440] => Array
                        (
                            [name] => Hero_Flux.Alt4
                            [cname] => Uproar
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2442] => Array
                        (
                            [name] => Hero_Gauntlet.Alt5
                            [cname] => Ussuri
                            [cost] => 450
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2444] => Array
                        (
                            [name] => Hero_Gladiator.Alt6
                            [cname] => Riftshards Gladiator
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2446] => Array
                        (
                            [name] => Hero_Plant.Alt5
                            [cname] => Persian Manticore
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2448] => Array
                        (
                            [name] => Hero_Predator.Alt7
                            [cname] => Preda Tori
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2450] => Array
                        (
                            [name] => Hero_Parasite.Alt6
                            [cname] => Ellie Envy
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2452] => Array
                        (
                            [name] => Hero_Hunter.Alt7
                            [cname] => Bonnie Blood Hunter
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2454] => Array
                        (
                            [name] => Hero_Grinex.Alt5
                            [cname] => Lynn X
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2456] => Array
                        (
                            [name] => Hero_Monarch.Alt6
                            [cname] => Snowflake
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2458] => Array
                        (
                            [name] => Hero_Vindicator.Alt4
                            [cname] => Vindi the Gray
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2460] => Array
                        (
                            [name] => Hero_Bubbles.Alt9
                            [cname] => Big Boss
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2462] => Array
                        (
                            [name] => Hero_Hantumon.Alt6
                            [cname] => Leo
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2464] => Array
                        (
                            [name] => Hero_Martyr.Alt5
                            [cname] => Virgo
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2466] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt6
                            [cname] => Sagittarius
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2468] => Array
                        (
                            [name] => Hero_Ophelia.Alt4
                            [cname] => Capricorn
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2470] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt6
                            [cname] => Libra
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2472] => Array
                        (
                            [name] => Hero_Armadon.Alt6
                            [cname] => Scarlord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2474] => Array
                        (
                            [name] => Hero_Predator.Alt8
                            [cname] => Baal
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2476] => Array
                        (
                            [name] => Hero_Fairy.Alt4
                            [cname] => Beelzebub
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2480] => Array
                        (
                            [name] => Hero_Krixi.Alt4
                            [cname] => Lady Liberty
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2482] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt5
                            [cname] => Minos
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2484] => Array
                        (
                            [name] => Hero_Kraken.Alt4
                            [cname] => Cancer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2486] => Array
                        (
                            [name] => Hero_Ebulus.Alt5
                            [cname] => Scorpio
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2488] => Array
                        (
                            [name] => Hero_Silhouette.Alt5
                            [cname] => Minerva
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2492] => Array
                        (
                            [name] => Hero_Oogie.Alt4
                            [cname] => Boogie Oogie
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2494] => Array
                        (
                            [name] => Hero_Javaras.Alt5
                            [cname] => Aeacus
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2496] => Array
                        (
                            [name] => Hero_Accursed.Alt4
                            [cname] => Abaddon
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2498] => Array
                        (
                            [name] => Hero_Pearl.Alt6
                            [cname] => Aries
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2500] => Array
                        (
                            [name] => Hero_Frosty.Alt5
                            [cname] => Snow Queen Shiva
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2502] => Array
                        (
                            [name] => Hero_Engineer.Alt5
                            [cname] => Mangler
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3239] => Array
                        (
                            [name] => Hero_Tarot.Alt6
                            [cname] => Trick or Treat Tarot
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2517] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt7
                            [cname] => Mistress of Arms
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2519] => Array
                        (
                            [name] => Hero_Gunblade.Alt6
                            [cname] => Gunclaw
                            [cost] => 450
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2521] => Array
                        (
                            [name] => Hero_DoctorRepulsor.pog_skin
                            [cname] => POG Doctor Repulsor
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2522] => Array
                        (
                            [name] => Hero_SirBenzington.Alt6
                            [cname] => Grizzington
                            [cost] => 560
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2524] => Array
                        (
                            [name] => Hero_Magmar.Alt6
                            [cname] => Scoria
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2526] => Array
                        (
                            [name] => Hero_Tempest.Alt5
                            [cname] => Golden Poseidon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2528] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt6
                            [cname] => Killer Beelzebub
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2530] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt6
                            [cname] => King Minos
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2532] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt6
                            [cname] => MechaKing
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2557] => Array
                        (
                            [name] => Hero_Oogie.Alt5
                            [cname] => Ogoh-ogoh
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2559] => Array
                        (
                            [name] => Hero_Silhouette.Alt6
                            [cname] => Hexa
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2561] => Array
                        (
                            [name] => Hero_Deadwood.Alt5
                            [cname] => Corn Stalker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2566] => Array
                        (
                            [name] => Hero_Behemoth.Alt5
                            [cname] => Rune Weaver
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2568] => Array
                        (
                            [name] => Hero_Bombardier.Alt5
                            [cname] => Barrage
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2570] => Array
                        (
                            [name] => Hero_Gladiator.Alt7
                            [cname] => Arctos
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2576] => Array
                        (
                            [name] => Hero_Kane.Alt
                            [cname] => 8-Bit Kane
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2578] => Array
                        (
                            [name] => Hero_Kane.Alt2
                            [cname] => Katana
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2580] => Array
                        (
                            [name] => Hero_Panda.pog_skin
                            [cname] => POG Pandamonium
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2581] => Array
                        (
                            [name] => Hero_SandWraith.pog_skin
                            [cname] => POG Sand Wraith
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2582] => Array
                        (
                            [name] => Hero_Predator.pog_skin
                            [cname] => POG Predator
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2583] => Array
                        (
                            [name] => Hero_Hiro.pog_skin
                            [cname] => POG Swiftblade
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2584] => Array
                        (
                            [name] => Hero_BabaYaga.pog_skin
                            [cname] => POG Wretched Hag
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2589] => Array
                        (
                            [name] => Hero_Kane.Alt4
                            [cname] => Septar
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2591] => Array
                        (
                            [name] => Hero_Silhouette.Alt8
                            [cname] => Lady Nak
                            [cost] => 495
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2593] => Array
                        (
                            [name] => Hero_Accursed.Alt5
                            [cname] => Lord of Locusts
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2595] => Array
                        (
                            [name] => Hero_Riftmage.Alt3
                            [cname] => Possessed Riftwalker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2597] => Array
                        (
                            [name] => Hero_Rhapsody.Alt4
                            [cname] => Thriller Rhapsody
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2599] => Array
                        (
                            [name] => Hero_Devourer.Alt9
                            [cname] => Bedsheet Devourer
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2601] => Array
                        (
                            [name] => Hero_Lodestone.Alt4
                            [cname] => Straw Man Lodestone
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2603] => Array
                        (
                            [name] => Hero_Scar.Alt4
                            [cname] => Raving Madman
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2621] => Array
                        (
                            [name] => Hero_Silhouette.Alt7
                            [cname] => Mae Nak
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2623] => Array
                        (
                            [name] => Hero_Kane.Alt3
                            [cname] => Invader Kane
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2625] => Array
                        (
                            [name] => Hero_Legionnaire.Alt8
                            [cname] => Savior Legionnaire
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2628] => Array
                        (
                            [name] => Hero_Artillery.Alt6
                            [cname] => Boggus
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2630] => Array
                        (
                            [name] => Hero_Valkyrie.Alt6
                            [cname] => Skiver
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2632] => Array
                        (
                            [name] => Hero_Valkyrie.Alt7
                            [cname] => Brunhild
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2634] => Array
                        (
                            [name] => Hero_Electrician.Alt5
                            [cname] => Killawatt
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2636] => Array
                        (
                            [name] => Hero_Chipper.Alt4
                            [cname] => Dredger
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2638] => Array
                        (
                            [name] => Hero_Ra.Alt6
                            [cname] => New Year's Eve Reborn Ra
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2640] => Array
                        (
                            [name] => Hero_Succubis.Alt4
                            [cname] => Mistletoe Succubus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2642] => Array
                        (
                            [name] => Hero_Mumra.Alt4
                            [cname] => Festive Pharaoh
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2644] => Array
                        (
                            [name] => Hero_Solstice.Alt6
                            [cname] => Savior Solstice
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2646] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt7
                            [cname] => Savior Hammerstorm
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2648] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt7
                            [cname] => Savior Emerald Warden
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2650] => Array
                        (
                            [name] => Hero_Dampeer.Alt5
                            [cname] => Invader Dampeer
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2652] => Array
                        (
                            [name] => Hero_Rocky.Alt5
                            [cname] => Savior Pebbles
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2654] => Array
                        (
                            [name] => Hero_Ravenor.Alt6
                            [cname] => Invader Ravenor
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2667] => Array
                        (
                            [name] => Hero_Plant.Alt6
                            [cname] => Bramble of the Bells
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2676] => Array
                        (
                            [name] => Hero_Calamity.Alt2
                            [cname] => Wynd
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2678] => Array
                        (
                            [name] => Hero_Calamity.Alt
                            [cname] => Cassie Calamity
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2681] => Array
                        (
                            [name] => Hero_Martyr.Alt6
                            [cname] => Grimm's Medic
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2683] => Array
                        (
                            [name] => Hero_Frosty.pog_skin
                            [cname] => POG Glacius
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2684] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt4
                            [cname] => Ghosts of Christmas
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2686] => Array
                        (
                            [name] => Hero_Scout.pog_skin
                            [cname] => POG Scout
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2728] => Array
                        (
                            [name] => Hero_Defiler.pog_skin
                            [cname] => POG Defiler
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2729] => Array
                        (
                            [name] => Hero_Ophelia.pog_skin
                            [cname] => POG Ophelia
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2730] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt7
                            [cname] => Eagle Rider
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2732] => Array
                        (
                            [name] => Hero_Rampage.Alt10
                            [cname] => White Orc
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2734] => Array
                        (
                            [name] => Hero_Yogi.Alt4
                            [cname] => Northman Werebear
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2736] => Array
                        (
                            [name] => Hero_Scout.Alt7
                            [cname] => Halfling Warrior
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2738] => Array
                        (
                            [name] => Hero_BabaYaga.Alt5
                            [cname] => Treasure Hunter Hag
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2911] => Array
                        (
                            [name] => Hero_Calamity.Alt3
                            [cname] => Monster Trainer
                            [cost] => 720
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2740] => Array
                        (
                            [name] => Hero_Fade.trophy_skin
                            [cname] => Trophy Fayde
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2742] => Array
                        (
                            [name] => Hero_Kenisis.Alt4
                            [cname] => Necrosis
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2744] => Array
                        (
                            [name] => Hero_Tarot.Alt4
                            [cname] => Death Dealer
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2746] => Array
                        (
                            [name] => Hero_Jereziah.pog_skin
                            [cname] => Pog Jeraziah
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2808] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt8
                            [cname] => Drunken Fool
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2753] => Array
                        (
                            [name] => Hero_Panda.Alt6
                            [cname] => Green Wood Ram
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2755] => Array
                        (
                            [name] => Hero_Dreadknight.Alt5
                            [cname] => Blackwal Salforis
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2757] => Array
                        (
                            [name] => Hero_Empath.Alt5
                            [cname] => Diao Chan
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2759] => Array
                        (
                            [name] => Hero_Nomad.Alt8
                            [cname] => Zhang Fei
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2761] => Array
                        (
                            [name] => Hero_Rally.Alt7
                            [cname] => Savior Rally
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2763] => Array
                        (
                            [name] => Hero_BabaYaga.Alt6
                            [cname] => Lady Sita
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2765] => Array
                        (
                            [name] => Hero_Kraken.pog_skin
                            [cname] => POG Kraken
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2767] => Array
                        (
                            [name] => Hero_BabaYaga.Alt7
                            [cname] => Ramayana Sita
                            [cost] => 380
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2771] => Array
                        (
                            [name] => Hero_Xalynx.pog_skin
                            [cname] => POG Torturer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2772] => Array
                        (
                            [name] => Hero_Voodoo.pog_skin
                            [cname] => POG Voodoo
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2773] => Array
                        (
                            [name] => Hero_Maliken.Alt6
                            [cname] => Cao Cao
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2775] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt7
                            [cname] => Lu Bu
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2779] => Array
                        (
                            [name] => Hero_Deadlift.Alt2
                            [cname] => Medevac
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2781] => Array
                        (
                            [name] => Hero_Deadlift.Alt
                            [cname] => The Grand Druid
                            [cost] => 640
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2796] => Array
                        (
                            [name] => Hero_Circe.Alt4
                            [cname] => Dewi Sri
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2798] => Array
                        (
                            [name] => Hero_Klanx.Alt5
                            [cname] => Shamrock Klanx
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2804] => Array
                        (
                            [name] => Hero_Treant.pog_skin
                            [cname] => POG Keeper of the Forest
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2805] => Array
                        (
                            [name] => Hero_Legionnaire.trophy_skin
                            [cname] => Trophy Legionnaire
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2810] => Array
                        (
                            [name] => Hero_Kunas.Alt7
                            [cname] => Fluffybringer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2812] => Array
                        (
                            [name] => Hero_Krixi.Alt5
                            [cname] => Gisele
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2817] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt6
                            [cname] => Sacrilege
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2819] => Array
                        (
                            [name] => Hero_Legionnaire.pog_skin
                            [cname] => POG Legionnaire
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2820] => Array
                        (
                            [name] => Hero_Hiro.Alt8
                            [cname] => Kissaki
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2824] => Array
                        (
                            [name] => Hero_Parallax.Alt
                            [cname] => Thai Warrior
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2826] => Array
                        (
                            [name] => Hero_Parallax.Alt2
                            [cname] => High Priestess
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2831] => Array
                        (
                            [name] => Hero_Gunblade.Alt7
                            [cname] => LightGunblade
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2833] => Array
                        (
                            [name] => Hero_Riptide.Alt4
                            [cname] => Chalawan
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2835] => Array
                        (
                            [name] => Hero_Magmar.Alt7
                            [cname] => Tidal Magmus
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2837] => Array
                        (
                            [name] => Hero_Engineer.Alt6
                            [cname] => Soaker Rosie
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2839] => Array
                        (
                            [name] => Hero_Soulstealer.pog_skin
                            [cname] => POG Soulstealer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2840] => Array
                        (
                            [name] => Hero_Hiro.trophy_skin
                            [cname] => Trophy Swiftblade
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2854] => Array
                        (
                            [name] => Hero_Devourer.Alt10
                            [cname] => Paku Devourer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2856] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt7
                            [cname] => Game Master
                            [cost] => 720
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2858] => Array
                        (
                            [name] => Hero_Tempest.pog_skin
                            [cname] => POG Tempest
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2876] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt5
                            [cname] => Dominion Shadowblade
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2878] => Array
                        (
                            [name] => Hero_Taint.Alt6
                            [cname] => Pixelkeeper
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2880] => Array
                        (
                            [name] => Hero_Rhapsody.Alt5
                            [cname] => DDRhapsody
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2882] => Array
                        (
                            [name] => Hero_Predator.Alt9
                            [cname] => Savior Predator
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2884] => Array
                        (
                            [name] => Hero_Vanya.pog_skin
                            [cname] => POG The Dark Lady
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2886] => Array
                        (
                            [name] => Hero_Engineer.Alt7
                            [cname] => Songkran Rosie
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2894] => Array
                        (
                            [name] => Hero_Pestilence.Alt5
                            [cname] => Invader Pestilence
                            [cost] => 800
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2896] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt8
                            [cname] => Waru
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2898] => Array
                        (
                            [name] => Hero_FlintBeastwood.trophy_skin
                            [cname] => Trophy Flint Beastwood
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2900] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt5
                            [cname] => Dr. Gamer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2903] => Array
                        (
                            [name] => Hero_Deadwood.pog_skin
                            [cname] => POG Deadwood
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2906] => Array
                        (
                            [name] => Hero_Solstice.Alt7
                            [cname] => The Twins
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2913] => Array
                        (
                            [name] => Hero_Behemoth.Alt6
                            [cname] => Atlas
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2915] => Array
                        (
                            [name] => Hero_Kunas.pog_skin
                            [cname] => POG Thunderbringer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3001] => Array
                        (
                            [name] => Hero_Javaras.Alt6
                            [cname] => Acheron of Mana
                            [cost] => 270
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2936] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt8
                            [cname] => Chang Mai
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2938] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt7
                            [cname] => Bangkok Slayer
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2940] => Array
                        (
                            [name] => Hero_Predator.Alt10
                            [cname] => Khon Kean Predator
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2942] => Array
                        (
                            [name] => Hero_Valkyrie.Alt8
                            [cname] => Phuket Valkyrie
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2944] => Array
                        (
                            [name] => Hero_MasterOfArms.trophy_skin
                            [cname] => Trophy Master of Arms
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2946] => Array
                        (
                            [name] => Hero_Gladiator.pog_skin
                            [cname] => POG Gladiator
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2978] => Array
                        (
                            [name] => Hero_Skrap.Alt
                            [cname] => Bone Collector
                            [cost] => 225
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2980] => Array
                        (
                            [name] => Hero_Skrap.Alt2
                            [cname] => Warlock
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2982] => Array
                        (
                            [name] => Hero_Scout.Alt8
                            [cname] => Continental Rebel
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2984] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt10
                            [cname] => Redcoat Flint
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2986] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt8
                            [cname] => Carnystorm
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2988] => Array
                        (
                            [name] => Hero_Silhouette.Alt9
                            [cname] => Cirque du Silhouette
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2990] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt8
                            [cname] => Freakshow
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2992] => Array
                        (
                            [name] => Hero_Calamity.Alt4
                            [cname] => Carnage Calamity
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2994] => Array
                        (
                            [name] => Hero_Midas.Alt6
                            [cname] => Sterling Midas
                            [cost] => 9006
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2996] => Array
                        (
                            [name] => Hero_Hammerstorm.pog_skin
                            [cname] => POG Hammerstorm
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3003] => Array
                        (
                            [name] => Hero_Behemoth.Alt7
                            [cname] => Surfer Dude Behemoth
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3005] => Array
                        (
                            [name] => Hero_Rhapsody.Alt6
                            [cname] => Luau Rhapsody
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3007] => Array
                        (
                            [name] => Hero_Valkyrie.Alt9
                            [cname] => Beach Babe Valk
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3009] => Array
                        (
                            [name] => Hero_Solstice.trophy_skin
                            [cname] => Trophy Solstice
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3011] => Array
                        (
                            [name] => Hero_Scar.pog_skin
                            [cname] => POG Madman
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3022] => Array
                        (
                            [name] => Hero_Empath.Alt7
                            [cname] => Emerald Paragon Empath
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3037] => Array
                        (
                            [name] => Hero_Tarot.Alt5
                            [cname] => Beach Volleyball Tarot
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3039] => Array
                        (
                            [name] => Hero_Kane.Alt5
                            [cname] => Lifeguard Kane
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3041] => Array
                        (
                            [name] => Hero_SandWraith.Alt5
                            [cname] => Surf Wraith
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3043] => Array
                        (
                            [name] => Hero_Kunas.Alt8
                            [cname] => The Five Thunder Emperors
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3045] => Array
                        (
                            [name] => Hero_WolfMan.pog_skin
                            [cname] => POG War Beast
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3046] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt5
                            [cname] => Forsaken Death Prowler
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3065] => Array
                        (
                            [name] => Hero_Artillery.Alt7
                            [cname] => Srikandi
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3067] => Array
                        (
                            [name] => Hero_Accursed.Alt6
                            [cname] => Rahwana
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3069] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt9
                            [cname] => Dalang
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3071] => Array
                        (
                            [name] => Hero_Ellonia.Alt5
                            [cname] => Floral Ellonia
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3073] => Array
                        (
                            [name] => Hero_Arachna.Alt4
                            [cname] => Arachnae
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3075] => Array
                        (
                            [name] => Hero_Valkyrie.trophy_skin
                            [cname] => Trophy Valkyrie
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3077] => Array
                        (
                            [name] => Hero_Engineer.pog_skin
                            [cname] => POG Engineer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3078] => Array
                        (
                            [name] => Hero_Parasite.Alt5
                            [cname] => Amethyst Paragon Parasite
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3086] => Array
                        (
                            [name] => Hero_Berzerker.Alt7
                            [cname] => Erik the Red
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3089] => Array
                        (
                            [name] => Hero_Rocky.Alt6
                            [cname] => Rocky
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3091] => Array
                        (
                            [name] => Hero_Gauntlet.Alt6
                            [cname] => Mr. Marvelous
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3093] => Array
                        (
                            [name] => Hero_Pyromancer.Alt6
                            [cname] => Blaze
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3095] => Array
                        (
                            [name] => Hero_Scout.Alt9
                            [cname] => The Vanishing Woman
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3097] => Array
                        (
                            [name] => Hero_Nomad.Alt9
                            [cname] => Hang Jebat
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3099] => Array
                        (
                            [name] => Hero_HellDemon.pog_skin
                            [cname] => POG Soulreaper
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3101] => Array
                        (
                            [name] => Hero_Fade.Alt4
                            [cname] => Red Mist
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3105] => Array
                        (
                            [name] => Hero_Scar.Alt5
                            [cname] => MadCat Madman
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3107] => Array
                        (
                            [name] => Hero_Behemoth.Alt8
                            [cname] => Construction Worker Behemoth
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3109] => Array
                        (
                            [name] => Hero_Ra.Alt7
                            [cname] => Karnak the Tomb Guardian
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3111] => Array
                        (
                            [name] => Hero_Dampeer.Alt6
                            [cname] => Bloodthirsty Dampeer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3113] => Array
                        (
                            [name] => Hero_Pyromancer.trophy_skin
                            [cname] => Trophy Pyromancer
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3115] => Array
                        (
                            [name] => Hero_PollywogPriest.pog_skin
                            [cname] => POG Pollywog Priest
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3116] => Array
                        (
                            [name] => Hero_Riftmage.Alt4
                            [cname] => Opal Paragon Riftwalker
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3125] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt8
                            [cname] => Mountain Dew Monkey King
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3127] => Array
                        (
                            [name] => Hero_Rhapsody.Alt7
                            [cname] => Tourmaline Paragon Rhapsody
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3135] => Array
                        (
                            [name] => Hero_Succubis.Alt5
                            [cname] => Headmistress
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3137] => Array
                        (
                            [name] => Hero_Vindicator.Alt7
                            [cname] => Necronomicon Vindicator
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3139] => Array
                        (
                            [name] => Hero_Prisoner.Alt6
                            [cname] => Rune Breaker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3141] => Array
                        (
                            [name] => Hero_Gladiator.Alt8
                            [cname] => Vanquish
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3143] => Array
                        (
                            [name] => Hero_Pestilence.Alt6
                            [cname] => Carrion Beetle
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3145] => Array
                        (
                            [name] => Hero_Maliken.pog_skin
                            [cname] => POG Maliken
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3156] => Array
                        (
                            [name] => Hero_Nitro.Alt2
                            [cname] => Danse Macabre
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3158] => Array
                        (
                            [name] => Hero_Nitro.Alt
                            [cname] => Marauder
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3181] => Array
                        (
                            [name] => Hero_Valkyrie.Alt10
                            [cname] => Svana
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3183] => Array
                        (
                            [name] => Hero_Bushwack.Alt4
                            [cname] => Cesspool
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3185] => Array
                        (
                            [name] => Hero_Prophet.Alt6
                            [cname] => Amadea
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3187] => Array
                        (
                            [name] => Hero_Hantumon.Alt7
                            [cname] => Fright Hound
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3189] => Array
                        (
                            [name] => Hero_Hellbringer.Alt6
                            [cname] => Arimane the Pit Lord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3191] => Array
                        (
                            [name] => Hero_Ra.trophy_skin
                            [cname] => Trophy Amun Ra
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3193] => Array
                        (
                            [name] => Hero_DiseasedRider.pog_skin
                            [cname] => POG Plague Rider
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3194] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt11
                            [cname] => Hired Gun Flint
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3556] => Array
                        (
                            [name] => Hero_Silhouette.Alt10
                            [cname] => Hunter Silhouette
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3220] => Array
                        (
                            [name] => Hero_Devourer.Alt11
                            [cname] => Keelhaul Devourer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3222] => Array
                        (
                            [name] => Hero_Scout.Alt10
                            [cname] => Adkarna Assassin
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3224] => Array
                        (
                            [name] => Hero_Calamity.Alt5
                            [cname] => Rhadamanthus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3226] => Array
                        (
                            [name] => Hero_Rally.Alt8
                            [cname] => Blightstalker Rally
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3228] => Array
                        (
                            [name] => Hero_Legionnaire.Alt10
                            [cname] => Mercenary Legionnaire
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3230] => Array
                        (
                            [name] => Hero_PuppetMaster.pog_skin
                            [cname] => POG Puppet Master
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3231] => Array
                        (
                            [name] => Hero_Frosty.Alt6
                            [cname] => Zircon Paragon Glacius
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3241] => Array
                        (
                            [name] => Hero_Magmar.trophy_skin
                            [cname] => Trophy Magmus
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 100
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3243] => Array
                        (
                            [name] => Hero_Parasite.trophy_skin
                            [cname] => Trophy Parasite
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3248] => Array
                        (
                            [name] => Hero_Revenant.Alt4
                            [cname] => Azurite
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3256] => Array
                        (
                            [name] => Hero_Gauntlet.Alt7
                            [cname] => Polyphemus
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3258] => Array
                        (
                            [name] => Hero_Xalynx.Alt5
                            [cname] => Mermaid Torturer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3260] => Array
                        (
                            [name] => Hero_Fade.Alt5
                            [cname] => Persephone
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3262] => Array
                        (
                            [name] => Hero_Treant.Alt6
                            [cname] => Keeper of the Harvest
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3265] => Array
                        (
                            [name] => Hero_Yogi.pog_skin
                            [cname] => POG Wildsoul
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3266] => Array
                        (
                            [name] => Hero_Bombardier.Alt7
                            [cname] => Siam Warrior Bombardier
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3268] => Array
                        (
                            [name] => Hero_Rampage.Alt11
                            [cname] => Siam Warrior Rampage
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3270] => Array
                        (
                            [name] => Hero_Hiro.Alt10
                            [cname] => Siam Warrior Swiftblade
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3273] => Array
                        (
                            [name] => Hero_Bombardier.Alt6
                            [cname] => Yi Peng
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3275] => Array
                        (
                            [name] => Hero_Maliken.Alt7
                            [cname] => Adkarna King
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3277] => Array
                        (
                            [name] => Hero_Taint.Alt7
                            [cname] => Holidaykeeper Hestia
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3279] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt6
                            [cname] => Siam Warrior Forsaken Archer
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3281] => Array
                        (
                            [name] => Hero_Legionnaire.Alt11
                            [cname] => Siam Warrior Legionnaire
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3283] => Array
                        (
                            [name] => Hero_Voodoo.Alt5
                            [cname] => Siam Warrior Voodoo Jester
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3285] => Array
                        (
                            [name] => Hero_Jereziah.Alt6
                            [cname] => Blade of Sol
                            [cost] => 760
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3287] => Array
                        (
                            [name] => Hero_Shaman.pog_skin
                            [cname] => POG Demented Shaman
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3295] => Array
                        (
                            [name] => Hero_Gauntlet.pog_skin
                            [cname] => POG Gauntlet
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3296] => Array
                        (
                            [name] => Hero_Kane.Alt6
                            [cname] => Candy Kane
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3298] => Array
                        (
                            [name] => Hero_Andromeda.Alt4
                            [cname] => Christmas Lights Andromeda
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3300] => Array
                        (
                            [name] => Hero_Riptide.Alt6
                            [cname] => Yuletide
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3302] => Array
                        (
                            [name] => Hero_Rhapsody.Alt8
                            [cname] => Christmas Carol
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3304] => Array
                        (
                            [name] => Hero_Ra.Alt8
                            [cname] => Bask in My Presents Ra
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3306] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt8
                            [cname] => Lapis Lazuli Paragon Witch Slaye
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3319] => Array
                        (
                            [name] => Hero_Nitro.Alt3
                            [cname] => Bosozoku Nitro
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3321] => Array
                        (
                            [name] => Hero_Bushwack.Alt5
                            [cname] => Siam Warrior Bushwack
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3323] => Array
                        (
                            [name] => Hero_Kane.Alt7
                            [cname] => Siam Warrior Kane
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3325] => Array
                        (
                            [name] => Hero_Skrap.Alt3
                            [cname] => Siam Warrior Skrap
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3339] => Array
                        (
                            [name] => Hero_KingKlout.Alt2
                            [cname] => King Truffle
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3341] => Array
                        (
                            [name] => Hero_KingKlout.Alt
                            [cname] => King Klaus
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3346] => Array
                        (
                            [name] => Hero_Gemini.Alt5
                            [cname] => Lion of Sol
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3348] => Array
                        (
                            [name] => Hero_Artesia.Alt5
                            [cname] => Mechartesia
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3350] => Array
                        (
                            [name] => Hero_Gladiator.Alt9
                            [cname] => Gladiclaus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3352] => Array
                        (
                            [name] => Hero_Rocky.Alt7
                            [cname] => Boulderdash
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3354] => Array
                        (
                            [name] => Hero_Valkyrie.Alt11
                            [cname] => Adkarna Valkyrie
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3356] => Array
                        (
                            [name] => Hero_Pearl.Alt7
                            [cname] => Snowglobe
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3358] => Array
                        (
                            [name] => Hero_Blitz.Alt4
                            [cname] => Blitzen
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3360] => Array
                        (
                            [name] => Hero_Pestilence.Alt7
                            [cname] => Lord Pestilence
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3362] => Array
                        (
                            [name] => Hero_Yogi.Alt5
                            [cname] => Tigersoul
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3364] => Array
                        (
                            [name] => Hero_Berzerker.Alt8
                            [cname] => Bloodaxe Berzerker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3366] => Array
                        (
                            [name] => Hero_Ophelia.Alt5
                            [cname] => Pan
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3368] => Array
                        (
                            [name] => Hero_WitchSlayer.trophy_skin
                            [cname] => Trophy Witch Slayer
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3372] => Array
                        (
                            [name] => Hero_BabaYaga.Alt8
                            [cname] => Alexandrite Paragon Wretched Hag
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3380] => Array
                        (
                            [name] => Hero_Ebulus.pog_skin
                            [cname] => POG Slither
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3381] => Array
                        (
                            [name] => Hero_Hellbringer.pog_skin
                            [cname] => POG Hellbringer
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3409] => Array
                        (
                            [name] => Hero_Gauntlet.Alt8
                            [cname] => Invader Gauntlet
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3411] => Array
                        (
                            [name] => Hero_Rocky.Alt8
                            [cname] => Siege Golem Pebbles
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3413] => Array
                        (
                            [name] => Hero_Kane.Alt9
                            [cname] => Uschi
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3415] => Array
                        (
                            [name] => Hero_Mumra.Alt5
                            [cname] => Steam Knight Pharaoh
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3417] => Array
                        (
                            [name] => Hero_Artillery.Alt8
                            [cname] => Ravus
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3419] => Array
                        (
                            [name] => Hero_Arachna.Alt5
                            [cname] => Black Widow
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3421] => Array
                        (
                            [name] => Hero_Bubbles.Alt10
                            [cname] => Steam Mage Bubbles
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3423] => Array
                        (
                            [name] => Hero_Behemoth.Alt10
                            [cname] => Carnelian Paragon Behemoth
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3436] => Array
                        (
                            [name] => Hero_Magmar.pog_skin
                            [cname] => POG Magmus
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3437] => Array
                        (
                            [name] => Hero_FlameDragon.Alt8
                            [cname] => Knightslayer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3439] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt5
                            [cname] => Inquisitor
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3441] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt9
                            [cname] => Unbound Monkey King
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3443] => Array
                        (
                            [name] => Hero_Kenisis.Alt5
                            [cname] => Nian Guardian Kinesis
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3445] => Array
                        (
                            [name] => Hero_Panda.Alt9
                            [cname] => Nian Guardian Pandamonium
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3447] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt10
                            [cname] => Topaz Paragon Puppet Master
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3453] => Array
                        (
                            [name] => Hero_Xalynx.Alt6
                            [cname] => Bloodstone Paragon Torturer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3459] => Array
                        (
                            [name] => Hero_Nomad.trophy_skin
                            [cname] => Trophy Nomad
                            [cost] => 9005
                            [premium] => 1
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3467] => Array
                        (
                            [name] => Hero_Rhapsody.Alt9
                            [cname] => Zhaojun
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3469] => Array
                        (
                            [name] => Hero_Krixi.Alt7
                            [cname] => Nian Guardian Moon Queen
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3486] => Array
                        (
                            [name] => Hero_Valkyrie.pog_skin
                            [cname] => POG Valkyrie
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3487] => Array
                        (
                            [name] => Hero_Fade.Alt8
                            [cname] => Shadowkiller
                            [cost] => 9002
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3489] => Array
                        (
                            [name] => Hero_Empath.Alt8
                            [cname] => Overly Attached Empath
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3491] => Array
                        (
                            [name] => Hero_Andromeda.Alt5
                            [cname] => Eos
                            [cost] => 270
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3493] => Array
                        (
                            [name] => Hero_Succubis.Alt7
                            [cname] => High School Sweetheart
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3496] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt6
                            [cname] => Garnet Paragon Dr. Repulsor
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3975] => Array
                        (
                            [name] => Hero_Solstice.Alt8
                            [cname] => Spring Break Solstice
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3558] => Array
                        (
                            [name] => Hero_Calamity.Alt6
                            [cname] => Hunter Calamity
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3560] => Array
                        (
                            [name] => Hero_Engineer.Alt8
                            [cname] => Hunter Engineer
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3562] => Array
                        (
                            [name] => Hero_Tarot.Alt7
                            [cname] => Hunter Tarot
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3564] => Array
                        (
                            [name] => Hero_Voodoo.Alt6
                            [cname] => Hunter Voodoo Jester
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3566] => Array
                        (
                            [name] => Hero_FlameDragon.trophy_skin
                            [cname] => Trophy Draconis
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3568] => Array
                        (
                            [name] => Hero_Magmar.Alt9
                            [cname] => Spectrum Paragon Magmus
                            [cost] => 780
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3577] => Array
                        (
                            [name] => Hero_Tarot.trophy_skin
                            [cname] => Trophy Tarot
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3579] => Array
                        (
                            [name] => Hero_Moira.Alt3
                            [cname] => Arcanium Armor Moira
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3581] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt9
                            [cname] => Shamrock Mistress
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3583] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt9
                            [cname] => Adkarna Hammerguard
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3585] => Array
                        (
                            [name] => Hero_Legionnaire.Alt12
                            [cname] => Argentus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3587] => Array
                        (
                            [name] => Hero_Aluna.Alt5
                            [cname] => Spirit Warrior
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3589] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt5
                            [cname] => Dwarf Lord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3591] => Array
                        (
                            [name] => Hero_Midas.Alt7
                            [cname] => Warrior King Midas
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3599] => Array
                        (
                            [name] => Hero_Tarot.Alt8
                            [cname] => Harlequin Tarot
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3601] => Array
                        (
                            [name] => Hero_Devourer.Alt12
                            [cname] => Easter Egg Devourer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3603] => Array
                        (
                            [name] => Hero_Bombardier.Alt8
                            [cname] => Oderr the Fiery Viking
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3605] => Array
                        (
                            [name] => Hero_Ravenor.Alt7
                            [cname] => Ravenna
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3607] => Array
                        (
                            [name] => Hero_Rocky.Alt9
                            [cname] => Easter Island Pebbles
                            [cost] => 380
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3899] => Array
                        (
                            [name] => Hero_Blitz.Alt5
                            [cname] => Songkran Blitz
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3901] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt6
                            [cname] => Songkran Disciple
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3903] => Array
                        (
                            [name] => Hero_Taint.Alt8
                            [cname] => Songkran Hestia
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3905] => Array
                        (
                            [name] => Hero_Shaman.Alt7
                            [cname] => Songkran Athena
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3907] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt8
                            [cname] => Songkran Archer
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3909] => Array
                        (
                            [name] => Hero_Shellshock.Alt2
                            [cname] => Ol' Packsnail
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3911] => Array
                        (
                            [name] => Hero_Shellshock.Alt
                            [cname] => Crochetshock
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3913] => Array
                        (
                            [name] => Hero_Hantumon.Alt9
                            [cname] => Ferocious Leo
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3940] => Array
                        (
                            [name] => Hero_Armadon.set_ascension
                            [cname] => Ascension Armadon
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3942] => Array
                        (
                            [name] => Hero_Mumra.set_ascension
                            [cname] => Ascension Pharaoh
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3944] => Array
                        (
                            [name] => Hero_Parallax.set_ascension
                            [cname] => Ascension Parallax
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3946] => Array
                        (
                            [name] => Hero_Ebulus.Alt6
                            [cname] => Red Scorpio Slither
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3948] => Array
                        (
                            [name] => Hero_Bephelgor.Alt5
                            [cname] => Seasick Balphagore
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3950] => Array
                        (
                            [name] => Hero_Parasite.set_ascension
                            [cname] => Ascension Parasite
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3952] => Array
                        (
                            [name] => Hero_Magmar.set_ascension
                            [cname] => Ascension Magmus
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3954] => Array
                        (
                            [name] => Hero_Scout.trophy_skin
                            [cname] => Trophy Scout
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4019] => Array
                        (
                            [name] => Hero_Vanya.set_ascension
                            [cname] => Ascension Dark Lady
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3977] => Array
                        (
                            [name] => Hero_Magmar.Alt10
                            [cname] => Swagmus
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3979] => Array
                        (
                            [name] => Hero_Hydromancer.Alt6
                            [cname] => ALPHA Myrmidon
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3981] => Array
                        (
                            [name] => Hero_Hunter.Alt8
                            [cname] => ALPHA Blood Hunter
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3983] => Array
                        (
                            [name] => Hero_Kunas.Alt9
                            [cname] => ALPHA Thunderbringer
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3985] => Array
                        (
                            [name] => Hero_Defiler.set_ascension
                            [cname] => Ascension Defiler
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3987] => Array
                        (
                            [name] => Hero_Soulstealer.set_ascension
                            [cname] => Ascension Soulstealer
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4008] => Array
                        (
                            [name] => Hero_DoctorRepulsor.set_ascent
                            [cname] => Ascension Dr. Repulsor
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4010] => Array
                        (
                            [name] => Hero_Fade.set_ascension
                            [cname] => Ascension Fayde
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4012] => Array
                        (
                            [name] => Hero_Bubbles.Alt11
                            [cname] => ALPHA Bubbles
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4014] => Array
                        (
                            [name] => Hero_Tundra.Alt5
                            [cname] => ALPHA Tundra
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4016] => Array
                        (
                            [name] => Hero_Predator.Alt11
                            [cname] => ALPHA Predator
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4021] => Array
                        (
                            [name] => Hero_Salomon.set_ascension
                            [cname] => Ascension Salomon
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4023] => Array
                        (
                            [name] => Hero_Artillery.set_ascension
                            [cname] => Ascension Artillery
                            [cost] => 315
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4025] => Array
                        (
                            [name] => Hero_Deadlift.Alt3
                            [cname] => Riftspawn Deadlift
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4027] => Array
                        (
                            [name] => Hero_Ellonia.Alt6
                            [cname] => Black Ice Ellonia
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4029] => Array
                        (
                            [name] => Hero_Javaras.Alt7
                            [cname] => Dark Mana Mage
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4031] => Array
                        (
                            [name] => Hero_Lodestone.Alt5
                            [cname] => Goalie Lodestone
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4033] => Array
                        (
                            [name] => Hero_Kane.Alt11
                            [cname] => Sudden Death Kane
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4035] => Array
                        (
                            [name] => Hero_Rocky.Alt11
                            [cname] => Stonewall Pebbles
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4052] => Array
                        (
                            [name] => Hero_Pestilence.soccer_skin
                            [cname] => Soccer Pestilence
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4054] => Array
                        (
                            [name] => Hero_Geomancer.soccer_skin
                            [cname] => Soccer Geomancer
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4056] => Array
                        (
                            [name] => Hero_Andromeda.soccer_skin
                            [cname] => Soccer Andromeda
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4058] => Array
                        (
                            [name] => Hero_Behemoth.Alt12
                            [cname] => Anhur
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4060] => Array
                        (
                            [name] => Hero_Electrician.Alt6
                            [cname] => Osiris Reborn
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4062] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt11
                            [cname] => Breakaway Monkey King
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4064] => Array
                        (
                            [name] => Hero_Zephyr.Alt9
                            [cname] => Winger Zephyr
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4066] => Array
                        (
                            [name] => Hero_KingKlout.Alt3
                            [cname] => Coach Klout
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4080] => Array
                        (
                            [name] => Hero_Pyromancer.Alt7
                            [cname] => Arsin Pyromancer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4082] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt6
                            [cname] => Daemon Highlord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4084] => Array
                        (
                            [name] => Hero_Riftmage.Alt5
                            [cname] => Pandora Riftwalker
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4086] => Array
                        (
                            [name] => Hero_Hiro.Alt9
                            [cname] => Captain of the Royal Guard
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4088] => Array
                        (
                            [name] => Hero_Jereziah.Alt8
                            [cname] => Ceremonial Armor Jeraziah
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4090] => Array
                        (
                            [name] => Hero_Rally.Alt9
                            [cname] => General
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4097] => Array
                        (
                            [name] => Hero_Ichor.Alt
                            [cname] => Umbra
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4099] => Array
                        (
                            [name] => Hero_Ichor.Alt2
                            [cname] => Aegis
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4101] => Array
                        (
                            [name] => Hero_Bushwack.Alt6
                            [cname] => Vuvuzela Bushwack
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4103] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt10
                            [cname] => Lion of the Gods Hercules
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4105] => Array
                        (
                            [name] => Hero_Vanya.Alt4
                            [cname] => The Dark Consort
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4107] => Array
                        (
                            [name] => Hero_Legionnaire.Alt13
                            [cname] => Royal Guardsman
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4127] => Array
                        (
                            [name] => Hero_Calamity.Alt9
                            [cname] => Mother of Dragons
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4129] => Array
                        (
                            [name] => Hero_Fade.Alt7
                            [cname] => Reaper
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4131] => Array
                        (
                            [name] => Hero_Kunas.Alt10
                            [cname] => Dark Lightninglord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4133] => Array
                        (
                            [name] => Hero_Gauntlet.Alt10
                            [cname] => Knockout Gauntlet
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4136] => Array
                        (
                            [name] => Hero_Flux.Alt6
                            [cname] => Cyborg
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4138] => Array
                        (
                            [name] => Hero_Kenisis.Alt6
                            [cname] => Esper
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4140] => Array
                        (
                            [name] => Hero_Scout.Alt11
                            [cname] => Velocity
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4142] => Array
                        (
                            [name] => Hero_Prisoner.Alt9
                            [cname] => Angel Style Prisoner
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4144] => Array
                        (
                            [name] => Hero_Dreadknight.Alt7
                            [cname] => Prince Salforis
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4155] => Array
                        (
                            [name] => Hero_Riptide.Alt7
                            [cname] => Deep Sea Riptide
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4157] => Array
                        (
                            [name] => Hero_Ra.Alt9
                            [cname] => Montu-Ra
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4159] => Array
                        (
                            [name] => Hero_Gemini.Alt6
                            [cname] => Nuri and Bryce
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4161] => Array
                        (
                            [name] => Hero_Frosty.Alt8
                            [cname] => Aurealis
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4163] => Array
                        (
                            [name] => Hero_Gunblade.Alt8
                            [cname] => Cyber Assassin
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4165] => Array
                        (
                            [name] => Hero_Mumra.Alt6
                            [cname] => Cyberian Husky
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4167] => Array
                        (
                            [name] => Hero_Ellonia.Alt7
                            [cname] => Da Qiao
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4169] => Array
                        (
                            [name] => Hero_Pearl.Alt8
                            [cname] => Xiao Qiao
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4171] => Array
                        (
                            [name] => Hero_Artillery.Alt10
                            [cname] => Huang Zhong
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4173] => Array
                        (
                            [name] => Hero_Berzerker.Alt11
                            [cname] => Xia Hou Dun
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4175] => Array
                        (
                            [name] => Hero_Vindicator.Alt10
                            [cname] => Si Ma Yi
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4177] => Array
                        (
                            [name] => Hero_SirBenzington.Alt9
                            [cname] => Zhao Yun
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4180] => Array
                        (
                            [name] => Hero_Hellbringer.Alt7
                            [cname] => Battlebringer
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4182] => Array
                        (
                            [name] => Hero_Prophet.Alt7
                            [cname] => Trickster Prophet
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4184] => Array
                        (
                            [name] => Hero_Defiler.Alt5
                            [cname] => The Green Lady Defiler
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4226] => Array
                        (
                            [name] => Hero_SandWraith.Alt9
                            [cname] => Khamsin
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4192] => Array
                        (
                            [name] => Hero_Artillery.Alt9
                            [cname] => Huang Zhong (EN)
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4193] => Array
                        (
                            [name] => Hero_Berzerker.Alt10
                            [cname] => Xia Hou Dun (EN)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4194] => Array
                        (
                            [name] => Hero_Vindicator.Alt9
                            [cname] => Si Ma Yi (EN)
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4195] => Array
                        (
                            [name] => Hero_SirBenzington.Alt8
                            [cname] => Zhao Yun (EN)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4196] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt6
                            [cname] => Angel of Death
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4198] => Array
                        (
                            [name] => Hero_Krixi.Alt8
                            [cname] => Lunari
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4200] => Array
                        (
                            [name] => Hero_Xalynx.Alt7
                            [cname] => Misery
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4202] => Array
                        (
                            [name] => Hero_Accursed.Alt7
                            [cname] => Laboratory Accursed
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4221] => Array
                        (
                            [name] => Hero_Vanya.Alt5
                            [cname] => Cyber Vanya
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4223] => Array
                        (
                            [name] => Hero_Artillery.Alt11
                            [cname] => Cyber Artillery
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4228] => Array
                        (
                            [name] => Hero_Salomon.Alt5
                            [cname] => Shaytan
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4230] => Array
                        (
                            [name] => Hero_Armadon.Alt8
                            [cname] => Dreadmace
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4282] => Array
                        (
                            [name] => Hero_Fade.Alt6
                            [cname] => Cyber Fayde
                            [cost] => 495
                            [premium] => 1
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4290] => Array
                        (
                            [name] => Hero_EmeraldWarden.Alt9
                            [cname] => Daemon Dragoon
                            [cost] => 480
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4291] => Array
                        (
                            [name] => Hero_Hunter.Alt9
                            [cname] => Blood Fiend
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4294] => Array
                        (
                            [name] => Hero_Pestilence.Alt8
                            [cname] => Scourge Trooper
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4297] => Array
                        (
                            [name] => Hero_Adrenaline.Alt
                            [cname] => Sanctum
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4299] => Array
                        (
                            [name] => Hero_Adrenaline.Alt2
                            [cname] => Blade of Blackwal
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4301] => Array
                        (
                            [name] => Hero_Jereziah.Alt9
                            [cname] => The Iron King
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4887] => Array
                        (
                            [name] => Hero_Javaras.Alt8
                            [cname] => Tutankhamun
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4413] => Array
                        (
                            [name] => Hero_Chronos.Alt8
                            [cname] => Christmas Chronos
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4415] => Array
                        (
                            [name] => Hero_Shaman.Alt8
                            [cname] => Winter Shaman
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4417] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt12
                            [cname] => Flint Who Stole Xmas
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4419] => Array
                        (
                            [name] => Hero_Dampeer.Alt7
                            [cname] => Kannibal
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4421] => Array
                        (
                            [name] => Hero_Rampage.Alt13
                            [cname] => Gory Vanguard
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4423] => Array
                        (
                            [name] => Hero_Nomad.Alt11
                            [cname] => Bloodstorm
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4425] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt12
                            [cname] => Six Eared Macaque
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4427] => Array
                        (
                            [name] => Hero_Zephyr.Alt8
                            [cname] => Firestorm
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4433] => Array
                        (
                            [name] => Hero_Apex.Alt
                            [cname] => Zenith
                            [cost] => 315
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4435] => Array
                        (
                            [name] => Hero_Apex.Alt2
                            [cname] => Nadir
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4438] => Array
                        (
                            [name] => Hero_Soulstealer.Alt5
                            [cname] => Xmas Spirit Hades
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4440] => Array
                        (
                            [name] => Hero_Hydromancer.Alt5
                            [cname] => Mephisto Myrmidon
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4442] => Array
                        (
                            [name] => Hero_Hantumon.Alt10
                            [cname] => Catnip Night Hound
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4444] => Array
                        (
                            [name] => Hero_Midas.Alt9
                            [cname] => Circus Bear Goldie
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4446] => Array
                        (
                            [name] => Hero_Yogi.Alt6
                            [cname] => Lion Tamer Wildsoul
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4448] => Array
                        (
                            [name] => Hero_SirBenzington.Alt10
                            [cname] => Big Top Benzi
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4467] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt7
                            [cname] => Lion Dance Disciple
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4469] => Array
                        (
                            [name] => Hero_Armadon.Alt9
                            [cname] => God of Fortune
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4471] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt9
                            [cname] => Doctor Firecracker
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4473] => Array
                        (
                            [name] => Hero_Artesia.Alt6
                            [cname] => Yuanri
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4477] => Array
                        (
                            [name] => Hero_EmeraldWarden.trophy_skin
                            [cname] => Trophy Emerald Warden (Basic)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4484] => Array
                        (
                            [name] => Hero_EmeraldWarden.trophy_skin02
                            [cname] => Trophy Emerald Warden (Advanced)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4485] => Array
                        (
                            [name] => Hero_EmeraldWarden.trophy_skin03
                            [cname] => Trophy Emerald Warden (Elite)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4491] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt9
                            [cname] => Master of Hearts
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4493] => Array
                        (
                            [name] => Hero_Klanx.Alt7
                            [cname] => Prince Charming
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4495] => Array
                        (
                            [name] => Hero_Solstice.Alt9
                            [cname] => Yin and Yang
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4497] => Array
                        (
                            [name] => Hero_Bushwack.Alt7
                            [cname] => Mech Huntress
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4507] => Array
                        (
                            [name] => Hero_Pearl.Alt9
                            [cname] => Popcorn
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4509] => Array
                        (
                            [name] => Hero_FlameDragon.Alt9
                            [cname] => Draco
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4511] => Array
                        (
                            [name] => Hero_Parallax.Alt4
                            [cname] => Ion
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4513] => Array
                        (
                            [name] => Hero_Predator.Alt12
                            [cname] => Hack
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4515] => Array
                        (
                            [name] => Hero_Defiler.Alt6
                            [cname] => Krasue
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4517] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt11
                            [cname] => Mo-Phi
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4519] => Array
                        (
                            [name] => Hero_Hunter.Alt10
                            [cname] => Krahang
                            [cost] => 360
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4521] => Array
                        (
                            [name] => Hero_Magmar.Alt11
                            [cname] => Chocolate Magmousse
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4523] => Array
                        (
                            [name] => Hero_Tempest.Alt7
                            [cname] => Easter Elemental
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4527] => Array
                        (
                            [name] => Hero_Ra.Alt10
                            [cname] => Fusion Ra
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4529] => Array
                        (
                            [name] => Hero_Treant.Alt7
                            [cname] => Keeper of the blossoms
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4531] => Array
                        (
                            [name] => Hero_Bombardier.Alt9
                            [cname] => Songkran Bomb (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4533] => Array
                        (
                            [name] => Hero_Adrenaline.Alt3
                            [cname] => Songkran Adrenaline (EN)
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4535] => Array
                        (
                            [name] => Hero_Rocky.Alt10
                            [cname] => Chuck Pebbles
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4537] => Array
                        (
                            [name] => Hero_Fairy.Alt6
                            [cname] => Grace Nymphora
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4539] => Array
                        (
                            [name] => Hero_Empath.Alt9
                            [cname] => Nang Tani
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4541] => Array
                        (
                            [name] => Hero_Deadwood.Alt7
                            [cname] => Pret
                            [cost] => 360
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4572] => Array
                        (
                            [name] => Hero_Ebulus.Alt7
                            [cname] => Deep Poison Slither
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4575] => Array
                        (
                            [name] => Hero_Bombardier.Alt10
                            [cname] => Songkran Bomb
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4576] => Array
                        (
                            [name] => Hero_Adrenaline.Alt4
                            [cname] => Songkran Adrenaline
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4590] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt9
                            [cname] => Songkran Slayer (EN)
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4592] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt10
                            [cname] => Songkran Slayer
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4593] => Array
                        (
                            [name] => Hero_Behemoth.Alt13
                            [cname] => Plushie Behe
                            [cost] => 450
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4594] => Array
                        (
                            [name] => Hero_Grinex.Alt7
                            [cname] => Songkran Grinex
                            [cost] => 405
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4596] => Array
                        (
                            [name] => Hero_Grinex.Alt6
                            [cname] => Songkran Grinex (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4597] => Array
                        (
                            [name] => Hero_Shellshock.Alt4
                            [cname] => Songkran Shellshock
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4599] => Array
                        (
                            [name] => Hero_Shellshock.Alt3
                            [cname] => Songkran Shellshock (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4601] => Array
                        (
                            [name] => Hero_Behemoth.Alt14
                            [cname] => Misfit Behe
                            [cost] => 270
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4603] => Array
                        (
                            [name] => Hero_Revenant.Alt6
                            [cname] => Wendigo
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4613] => Array
                        (
                            [name] => Hero_Hantumon.Alt11
                            [cname] => Plushie Night Hound
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4615] => Array
                        (
                            [name] => Hero_Hantumon.Alt12
                            [cname] => Misfit Night Hound
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4617] => Array
                        (
                            [name] => Hero_Monarch.Alt7
                            [cname] => EXO Monarch
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4619] => Array
                        (
                            [name] => Hero_Maliken.Alt8
                            [cname] => Fusion Maliken
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4621] => Array
                        (
                            [name] => Hero_Devourer.Alt13
                            [cname] => Plushie Devo
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4623] => Array
                        (
                            [name] => Hero_Devourer.Alt14
                            [cname] => Misfit Devo
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4625] => Array
                        (
                            [name] => Hero_Fairy.trophy_skin
                            [cname] => Trophy Nymphora (Basic)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4627] => Array
                        (
                            [name] => Hero_Fairy.trophy_skin02
                            [cname] => Trophy Nymphora (Advanced)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4629] => Array
                        (
                            [name] => Hero_Fairy.trophy_skin03
                            [cname] => Trophy Nymphora (Elite)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4636] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt7
                            [cname] => Plushie Cthulu
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4638] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt8
                            [cname] => Misfit Cthulu
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4640] => Array
                        (
                            [name] => Hero_Pestilence.Alt9
                            [cname] => Plushie Pesti
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4642] => Array
                        (
                            [name] => Hero_Pestilence.Alt10
                            [cname] => Misfit Pesti
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4644] => Array
                        (
                            [name] => Hero_Gunblade.Alt9
                            [cname] => Gunmaiden
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4646] => Array
                        (
                            [name] => Hero_Legionnaire.Alt15
                            [cname] => Maritime Legionnaire
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4648] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt7
                            [cname] => Forsaken Siren
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4650] => Array
                        (
                            [name] => Hero_Aluna.Alt7
                            [cname] => The Emerald Princess
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4652] => Array
                        (
                            [name] => Hero_Parasite.Alt8
                            [cname] => Nuclear Parasite
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4654] => Array
                        (
                            [name] => Hero_Deadwood.Alt8
                            [cname] => Plushie Deadwood
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4656] => Array
                        (
                            [name] => Hero_Deadwood.Alt9
                            [cname] => Misfit Deadwood
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4658] => Array
                        (
                            [name] => Hero_Panda.Alt10
                            [cname] => Plushie Panda
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4660] => Array
                        (
                            [name] => Hero_Panda.Alt11
                            [cname] => Misfit Panda
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4662] => Array
                        (
                            [name] => Hero_Gladiator.Alt11
                            [cname] => All Hells Angel
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4664] => Array
                        (
                            [name] => Hero_Calamity.Alt8
                            [cname] => Archimedes Calamity
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4666] => Array
                        (
                            [name] => Hero_Hydromancer.Alt8
                            [cname] => Plushie Myrmidon
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4668] => Array
                        (
                            [name] => Hero_Hydromancer.Alt7
                            [cname] => Misfit Myrmidon
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4670] => Array
                        (
                            [name] => Hero_Bubbles.Alt12
                            [cname] => Plushie Bubbles
                            [cost] => 840
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4672] => Array
                        (
                            [name] => Hero_Bubbles.Alt13
                            [cname] => Misfit Bubbles
                            [cost] => 840
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4674] => Array
                        (
                            [name] => Hero_Soulstealer.Alt6
                            [cname] => EXO Soulstealer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4676] => Array
                        (
                            [name] => Hero_Scout.Alt12
                            [cname] => Vardik Scout
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4678] => Array
                        (
                            [name] => Hero_Succubis.Alt6
                            [cname] => Incubus
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4747] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt13
                            [cname] => Monkey Singer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4749] => Array
                        (
                            [name] => Hero_Frosty.Alt7
                            [cname] => Wildfire Glacius
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4751] => Array
                        (
                            [name] => Hero_Kane.Alt10
                            [cname] => Mutineer Kane
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4755] => Array
                        (
                            [name] => Hero_Warchief.Alt2
                            [cname] => Hex
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4757] => Array
                        (
                            [name] => Hero_Warchief.Alt
                            [cname] => Purgatory
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4775] => Array
                        (
                            [name] => Hero_Dampeer.Alt8
                            [cname] => The Gentleman Killer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4777] => Array
                        (
                            [name] => Hero_FlameDragon.Alt10
                            [cname] => Dragoness
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4779] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt10
                            [cname] => El Maestro
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4817] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt11
                            [cname] => Punk Hammer
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4906] => Array
                        (
                            [name] => Hero_Nitro.Alt4
                            [cname] => Tesla Cannon Nitro
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4819] => Array
                        (
                            [name] => Hero_Ravenor.Alt8
                            [cname] => Punk Ravenor
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4821] => Array
                        (
                            [name] => Hero_Rampage.Alt14
                            [cname] => Punk Rampage
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4823] => Array
                        (
                            [name] => Hero_Pyromancer.Alt8
                            [cname] => Punk Pyro
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4825] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt6
                            [cname] => Punk Smith
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4827] => Array
                        (
                            [name] => Hero_Nomad.Alt12
                            [cname] => Punk Nomad
                            [cost] => 9009
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4829] => Array
                        (
                            [name] => Hero_Valkyrie.Alt12
                            [cname] => Punk Valk
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4838] => Array
                        (
                            [name] => Hero_Hiro.Alt12
                            [cname] => Punk Swifty
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4857] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt13
                            [cname] => Punk Flint
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4859] => Array
                        (
                            [name] => Hero_Chronos.Alt9
                            [cname] => Punk Chronos
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4861] => Array
                        (
                            [name] => Hero_PuppetMaster.Alt12
                            [cname] => The Sculptor
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4865] => Array
                        (
                            [name] => Hero_Rhapsody.Alt10
                            [cname] => Rhapsody Hatsune Miku Ver
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4879] => Array
                        (
                            [name] => Hero_Klanx.Alt8
                            [cname] => Firefighter Klanx
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4881] => Array
                        (
                            [name] => Hero_Shaman.Alt9
                            [cname] => Firefighter Shaman
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4897] => Array
                        (
                            [name] => Hero_Hunter.Alt11
                            [cname] => Fusion Hunter
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4898] => Array
                        (
                            [name] => Hero_Vanya.Alt6
                            [cname] => Vice
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4899] => Array
                        (
                            [name] => Hero_Geomancer.Alt6
                            [cname] => Leviathan
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4900] => Array
                        (
                            [name] => Hero_Cthulhuphant.trophy_skin
                            [cname] => Trophy Cthulhu (Basic)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4902] => Array
                        (
                            [name] => Hero_Cthulhuphant.trophy_skin02
                            [cname] => Trophy Cthulhu (Advanced)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4903] => Array
                        (
                            [name] => Hero_Cthulhuphant.trophy_skin03
                            [cname] => Trophy Cthulhu (Elite)
                            [cost] => 700
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4924] => Array
                        (
                            [name] => Hero_Tarot.Alt9
                            [cname] => Onmyoji
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4926] => Array
                        (
                            [name] => Hero_Arachna.Alt7
                            [cname] => Yokai Arachna
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4928] => Array
                        (
                            [name] => Hero_SirBenzington.Alt11
                            [cname] => Bajutsu Benzi
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4930] => Array
                        (
                            [name] => Hero_Flux.Alt5
                            [cname] => Force of Nature
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4938] => Array
                        (
                            [name] => Hero_Krixi.Alt9
                            [cname] => Moon
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4940] => Array
                        (
                            [name] => Hero_BabaYaga.Alt10
                            [cname] => Mercury
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4942] => Array
                        (
                            [name] => Hero_Salomon.Alt6
                            [cname] => Yokai Salomon
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4946] => Array
                        (
                            [name] => Hero_Sapphire.Alt
                            [cname] => Picaroon Sapphire
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4948] => Array
                        (
                            [name] => Hero_Sapphire.Alt2
                            [cname] => Kinetic Sapphire
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4950] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt9
                            [cname] => Mars
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4952] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt8
                            [cname] => Europa
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4954] => Array
                        (
                            [name] => Hero_Kunas.Alt11
                            [cname] => Raijin
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4999] => Array
                        (
                            [name] => Hero_Bubbles.Alt14
                            [cname] => Noppamas Bubbles
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5001] => Array
                        (
                            [name] => Hero_Armadon.Alt10
                            [cname] => Arma Donna
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5003] => Array
                        (
                            [name] => Hero_Magmar.Alt12
                            [cname] => Fireheart
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5005] => Array
                        (
                            [name] => Hero_Behemoth.Alt15
                            [cname] => EXO Behe
                            [cost] => 420
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5012] => Array
                        (
                            [name] => Hero_DrunkenMaster.Alt10
                            [cname] => Drunken Moonster
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5014] => Array
                        (
                            [name] => Hero_Silhouette.Alt12
                            [cname] => Venus
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5016] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt6
                            [cname] => Prince Polly
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5018] => Array
                        (
                            [name] => Hero_Cthulhuphant.Alt9
                            [cname] => HoN Tour Cthulhu
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5020] => Array
                        (
                            [name] => Hero_Bubbles.trophy_skin
                            [cname] => Trophy Bubbles (Basic)
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5022] => Array
                        (
                            [name] => Hero_Bubbles.trophy_skin02
                            [cname] => Trophy Bubbles (Advanced)
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5024] => Array
                        (
                            [name] => Hero_Bubbles.trophy_skin03
                            [cname] => Trophy Bubbles (Elite)
                            [cost] => 9005
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5126] => Array
                        (
                            [name] => Hero_Rocky.trophy_skin01
                            [cname] => Pebbles Tier ONE
                            [cost] => 4999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5116] => Array
                        (
                            [name] => Hero_Dreadknight.Alt8
                            [cname] => Techromancer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5118] => Array
                        (
                            [name] => Hero_Predator.Alt13
                            [cname] => Beast Predator
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5120] => Array
                        (
                            [name] => Hero_Empath.Alt10
                            [cname] => Beauty Empath
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5122] => Array
                        (
                            [name] => Hero_Ophelia.Alt6
                            [cname] => Queen of Adkarna
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5127] => Array
                        (
                            [name] => Hero_Rocky.trophy_skin02
                            [cname] => Pebbles Tier TWO
                            [cost] => 4999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5144] => Array
                        (
                            [name] => Hero_Dampeer.Alt9
                            [cname] => Vampeera
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5128] => Array
                        (
                            [name] => Hero_Rocky.trophy_skin03
                            [cname] => Pebbles Tier THREE
                            [cost] => 4999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5478] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Alt10
                            [cname] => Punk Dr. Repulsor
                            [cost] => 270
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5146] => Array
                        (
                            [name] => Hero_Solstice.Alt10
                            [cname] => Christmas Solstice
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5148] => Array
                        (
                            [name] => Hero_Berzerker.Alt12
                            [cname] => Plumb Crazy Zerker
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5150] => Array
                        (
                            [name] => Hero_Adrenaline.Alt5
                            [cname] => Puzzler
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5160] => Array
                        (
                            [name] => Hero_Bombardier.Alt11
                            [cname] => Short Fuse Bomber
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5162] => Array
                        (
                            [name] => Hero_Blitz.Alt6
                            [cname] => Power-Up Blitz
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5164] => Array
                        (
                            [name] => Hero_SandWraith.Alt10
                            [cname] => Storm Daughters
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5166] => Array
                        (
                            [name] => Hero_Lodestone.Alt6
                            [cname] => Tumbler
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5170] => Array
                        (
                            [name] => Hero_Goldenveil.Alt
                            [cname] => Lurx
                            [cost] => 495
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5172] => Array
                        (
                            [name] => Hero_Goldenveil.Alt2
                            [cname] => Copperhead
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5191] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt7
                            [cname] => Gamerblade
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5193] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt11
                            [cname] => Master of Commandos
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5195] => Array
                        (
                            [name] => Hero_Scout.Alt13
                            [cname] => Deranger
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5197] => Array
                        (
                            [name] => Hero_Chronos.Alt10
                            [cname] => Professor Tick Tock
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5199] => Array
                        (
                            [name] => Hero_Jereziah.Alt10
                            [cname] => Beast King
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5219] => Array
                        (
                            [name] => Hero_Rocky.Alt12
                            [cname] => P-800
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5209] => Array
                        (
                            [name] => Hero_WitchSlayer.Alt11
                            [cname] => Sin Slayer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5211] => Array
                        (
                            [name] => Hero_Devourer.Alt15
                            [cname] => Jiangshi Devo
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5213] => Array
                        (
                            [name] => Hero_Hydromancer.Alt9
                            [cname] => Scylla
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5215] => Array
                        (
                            [name] => Hero_Tempest.Alt8
                            [cname] => Elder Rift Tempest
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5233] => Array
                        (
                            [name] => Hero_Fade.Alt10
                            [cname] => Contessa Raze
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5235] => Array
                        (
                            [name] => Hero_Kenisis.Alt7
                            [cname] => Sakura
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5237] => Array
                        (
                            [name] => Hero_Pyromancer.Alt9
                            [cname] => Kojin
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5239] => Array
                        (
                            [name] => Hero_Prophet.Alt8
                            [cname] => Prophet Prince
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5241] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt14
                            [cname] => Shinobi Monkey King
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5244] => Array
                        (
                            [name] => Hero_Gladiator.Alt12
                            [cname] => Kusanagi Gladiator
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5246] => Array
                        (
                            [name] => Hero_Ravenor.Alt9
                            [cname] => Cyber Ravenor
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5248] => Array
                        (
                            [name] => Hero_DwarfMagi.Alt7
                            [cname] => Plinko Smith
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5250] => Array
                        (
                            [name] => Hero_Empath.trophy_skin01
                            [cname] => Empath Tier ONE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5252] => Array
                        (
                            [name] => Hero_Empath.trophy_skin02
                            [cname] => Empath Tier TWO
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5254] => Array
                        (
                            [name] => Hero_Empath.trophy_skin03
                            [cname] => Empath Tier THREE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5269] => Array
                        (
                            [name] => Hero_Frosty.Alt9
                            [cname] => Keybreaker
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5271] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt12
                            [cname] => Locksmasher
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5273] => Array
                        (
                            [name] => Hero_Hunter.Alt12
                            [cname] => Hannya Blood Hunter
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5290] => Array
                        (
                            [name] => Hero_Nomad.Alt13
                            [cname] => Songkran Nomad (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5294] => Array
                        (
                            [name] => Hero_Nomad.Alt14
                            [cname] => HoNWorld Nomad
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5296] => Array
                        (
                            [name] => Hero_Vindicator.Alt11
                            [cname] => HoNWorld Vindicator
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5298] => Array
                        (
                            [name] => Hero_Silhouette.Alt13
                            [cname] => F.L.E.X Silhouette
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5300] => Array
                        (
                            [name] => Hero_Legionnaire.Alt16
                            [cname] => F.L.E.X Legionnaire
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5315] => Array
                        (
                            [name] => Hero_Nomad.Alt15
                            [cname] => Songkran Nomad
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5323] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt14
                            [cname] => F.L.E.X Flint
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5325] => Array
                        (
                            [name] => Hero_Bushwack.Alt8
                            [cname] => F.L.E.X Bushwack
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5327] => Array
                        (
                            [name] => Hero_Behemoth.Alt16
                            [cname] => F.L.E.X Behemoth
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5329] => Array
                        (
                            [name] => Hero_Hammerstorm.Alt13
                            [cname] => F.L.E.X Hammerstorm
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5331] => Array
                        (
                            [name] => Hero_Goldenveil.Alt3
                            [cname] => Songkran Goldenveil (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5332] => Array
                        (
                            [name] => Hero_Goldenveil.Alt4
                            [cname] => Songkran Goldenveil
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5334] => Array
                        (
                            [name] => Hero_Dreadknight.Alt9
                            [cname] => Songkran Salforis (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5335] => Array
                        (
                            [name] => Hero_Dreadknight.Alt10
                            [cname] => Songkran Salforis
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5337] => Array
                        (
                            [name] => Hero_SirBenzington.Alt12
                            [cname] => Songkran Benzi (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5338] => Array
                        (
                            [name] => Hero_SirBenzington.Alt13
                            [cname] => Songkran Benzi
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5340] => Array
                        (
                            [name] => Hero_Mumra.Alt7
                            [cname] => Songkran Pharaoh (EN)
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5341] => Array
                        (
                            [name] => Hero_Mumra.Alt8
                            [cname] => Songkran Pharaoh
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5347] => Array
                        (
                            [name] => Hero_Chi.Alt
                            [cname] => Osho
                            [cost] => 495
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5348] => Array
                        (
                            [name] => Hero_Chi.Alt2
                            [cname] => Master Ka
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5359] => Array
                        (
                            [name] => Hero_Hiro.Alt13
                            [cname] => Deathbloom
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5361] => Array
                        (
                            [name] => Hero_Voodoo.Alt8
                            [cname] => Painkiller
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5371] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt10
                            [cname] => Yumi
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5373] => Array
                        (
                            [name] => Hero_Hantumon.Alt13
                            [cname] => Wildcat
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5375] => Array
                        (
                            [name] => Hero_Parallax.Alt6
                            [cname] => Cruxlord
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5391] => Array
                        (
                            [name] => Hero_Sapphire.Alt3
                            [cname] => Azure Dragon
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5393] => Array
                        (
                            [name] => Hero_Vanya.Alt7
                            [cname] => White Tiger
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5395] => Array
                        (
                            [name] => Hero_Tarot.Alt10
                            [cname] => Carhop Tarot
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5397] => Array
                        (
                            [name] => Hero_Andromeda.Alt6
                            [cname] => Nebula
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5407] => Array
                        (
                            [name] => Hero_Prophet.Alt9
                            [cname] => Vermilion Bird
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5409] => Array
                        (
                            [name] => Hero_Bubbles.Alt15
                            [cname] => Black Tortoise
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5411] => Array
                        (
                            [name] => Hero_DiseasedRider.Alt8
                            [cname] => Plume Rider
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5437] => Array
                        (
                            [name] => Hero_Rally.Alt11
                            [cname] => Kyugo
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5439] => Array
                        (
                            [name] => Hero_Magmar.Alt13
                            [cname] => Saji
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5441] => Array
                        (
                            [name] => Hero_Chipper.trophy_skin01
                            [cname] => Trophy Chipper Tier ONE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5443] => Array
                        (
                            [name] => Hero_Chipper.trophy_skin02
                            [cname] => Trophy Chipper Tier TWO
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5445] => Array
                        (
                            [name] => Hero_Chipper.trophy_skin03
                            [cname] => Trophy Chipper Tier THREE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5447] => Array
                        (
                            [name] => Hero_Dampeer.Alt10
                            [cname] => Wing-Back Dampeer
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5449] => Array
                        (
                            [name] => Hero_Scar.Alt8
                            [cname] => The Playmaker
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5451] => Array
                        (
                            [name] => Hero_Accursed.Alt8
                            [cname] => General Noroi
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5453] => Array
                        (
                            [name] => Hero_Salomon.Alt7
                            [cname] => Sha Wujing
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5455] => Array
                        (
                            [name] => Hero_Yogi.Soccer_skin
                            [cname] => Wild Sbornaya
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5470] => Array
                        (
                            [name] => Hero_Engineer.Alt9
                            [cname] => Ol' Briarpatch
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5472] => Array
                        (
                            [name] => Hero_Fade.Alt9
                            [cname] => Bloodshadow
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5474] => Array
                        (
                            [name] => Hero_Riptide.Alt8
                            [cname] => Mecha Mermaid
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5476] => Array
                        (
                            [name] => Hero_Circe.Alt5
                            [cname] => Exiled Circe
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5480] => Array
                        (
                            [name] => Hero_PollywogPriest.Alt7
                            [cname] => Punk Pollywog
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5494] => Array
                        (
                            [name] => Hero_Soulstealer.Alt7
                            [cname] => Soulchiller
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5507] => Array
                        (
                            [name] => Hero_Ebulus.Alt8
                            [cname] => Cake Snake
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5509] => Array
                        (
                            [name] => Hero_Predator.Alt14
                            [cname] => Birthday Basher
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5514] => Array
                        (
                            [name] => Hero_Mimix.Alt
                            [cname] => Unity
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5516] => Array
                        (
                            [name] => Hero_Mimix.Alt2
                            [cname] => Severance
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5530] => Array
                        (
                            [name] => Hero_Ellonia.Alt8
                            [cname] => Queen of Hearts
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5532] => Array
                        (
                            [name] => Hero_SandWraith.Alt11
                            [cname] => Wraith of Diamonds
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5542] => Array
                        (
                            [name] => Hero_Kane.Alt12
                            [cname] => Blade of Spades
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5544] => Array
                        (
                            [name] => Hero_Pyromancer.Alt10
                            [cname] => Burn Club Pyro
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5546] => Array
                        (
                            [name] => Hero_Solstice.Alt11
                            [cname] => Deuces
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5583] => Array
                        (
                            [name] => Hero_Oogie.trophy_skin01
                            [cname] => Oogie Tier ONE
                            [cost] => 2999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5584] => Array
                        (
                            [name] => Hero_Oogie.trophy_skin02
                            [cname] => Oogie Tier TWO
                            [cost] => 3999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5585] => Array
                        (
                            [name] => Hero_Oogie.trophy_skin03
                            [cname] => Oogie Tier THREE
                            [cost] => 4999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5586] => Array
                        (
                            [name] => Hero_Kraken.Alt6
                            [cname] => Killer Kraken
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5588] => Array
                        (
                            [name] => Hero_Aluna.Alt8
                            [cname] => Aluna Red Riding Hood
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5590] => Array
                        (
                            [name] => Hero_MasterOfArms.Alt12
                            [cname] => Big Bad MoA
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5603] => Array
                        (
                            [name] => Hero_Hiro.Alt14
                            [cname] => Suzaku Swiftblade
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5605] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt15
                            [cname] => Prodigy King
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5607] => Array
                        (
                            [name] => Hero_Maliken.Alt9
                            [cname] => Volto Maliken
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5609] => Array
                        (
                            [name] => Hero_Fairy.Alt7
                            [cname] => Hummingbird
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5611] => Array
                        (
                            [name] => Hero_Chronos.Alt11
                            [cname] => Little Benny
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5613] => Array
                        (
                            [name] => Hero_Sapphire.Alt4
                            [cname] => Geosynch Sapphire
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5615] => Array
                        (
                            [name] => Hero_Maliken.Alt9
                            [cname] => Volto Maliken
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5616] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt15
                            [cname] => Prodigy King
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5617] => Array
                        (
                            [name] => Hero_Hiro.Alt14
                            [cname] => Suzaku Swiftblade
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5618] => Array
                        (
                            [name] => Hero_Chronos.Alt10
                            [cname] => Professor Tick Tock
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5619] => Array
                        (
                            [name] => Hero_Jereziah.Alt10
                            [cname] => Beast King
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5620] => Array
                        (
                            [name] => Hero_Lodestone.Alt6
                            [cname] => Tumbler
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5621] => Array
                        (
                            [name] => Hero_Goldenveil.Alt
                            [cname] => Lurx
                            [cost] => 495
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5622] => Array
                        (
                            [name] => Hero_Goldenveil.Alt2
                            [cname] => Copperhead
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5623] => Array
                        (
                            [name] => Hero_ShadowBlade.Alt7
                            [cname] => Gamerblade
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5624] => Array
                        (
                            [name] => Hero_Hydromancer.Alt9
                            [cname] => Scylla
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5646] => Array
                        (
                            [name] => Hero_Chronos.trophy_skin01
                            [cname] => Chronos Tier ONE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5625] => Array
                        (
                            [name] => Hero_Pearl.Alt10
                            [cname] => Pumpkin Party Pearl
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5627] => Array
                        (
                            [name] => Hero_Dreadknight.Alt11
                            [cname] => Lord Samhain
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5629] => Array
                        (
                            [name] => Hero_Goldenveil.Alt5
                            [cname] => Roninveil
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5648] => Array
                        (
                            [name] => Hero_Chronos.trophy_skin02
                            [cname] => Chronos Tier TWO
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5650] => Array
                        (
                            [name] => Hero_Chronos.trophy_skin03
                            [cname] => Chronos Tier THREE
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9999
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5657] => Array
                        (
                            [name] => Hero_FlintBeastwood.Alt15
                            [cname] => Pill Popper Flint
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5659] => Array
                        (
                            [name] => Hero_Rocky.Alt13
                            [cname] => Diamante
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5661] => Array
                        (
                            [name] => Hero_ForsakenArcher.Alt11
                            [cname] => Santa's Little Archer
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5670] => Array
                        (
                            [name] => Hero_Adrenaline.Alt6
                            [cname] => Adrenaline High Roller
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5672] => Array
                        (
                            [name] => Hero_Valkyrie.Alt13
                            [cname] => Azrael
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5674] => Array
                        (
                            [name] => Hero_Javaras.Alt9
                            [cname] => Sword Dancer Magebane
                            [cost] => 380
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5825] => Array
                        (
                            [name] => Hero_Kunas.Alt12
                            [cname] => Thor (HD)
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5824] => Array
                        (
                            [name] => Hero_Plant.Classic
                            [cname] => Throwback Bramble
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5721] => Array
                        (
                            [name] => Hero_MonkeyKing.Classic
                            [cname] => Throwback Monkey King
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5722] => Array
                        (
                            [name] => Hero_Tarot.Classic
                            [cname] => Throwback Tarot
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5803] => Array
                        (
                            [name] => Hero_Aluna.Alt9
                            [cname] => Aluna (CN)
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5806] => Array
                        (
                            [name] => Hero_MonkeyKing.Alt16
                            [cname] => Jade Macaque
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5808] => Array
                        (
                            [name] => Hero_Mumra.Alt9
                            [cname] => Doge Anubis
                            [cost] => 480
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5810] => Array
                        (
                            [name] => Hero_Artillery.Alt12
                            [cname] => Demon Hunter Artillery
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5816] => Array
                        (
                            [name] => Hero_Bombardier.Alt12
                            [cname] => Santa Bombardier
                            [cost] => 180
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5818] => Array
                        (
                            [name] => Hero_Empath.AltHD
                            [cname] => Empath (CN)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5820] => Array
                        (
                            [name] => Hero_Rhapsody.AltHD
                            [cname] => Rhapsody (CN)
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5822] => Array
                        (
                            [name] => Hero_Riptide.Classic
                            [cname] => Throwback Riptide
                            [cost] => 90
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5826] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Alt9
                            [cname] => Loki (HD)
                            [cost] => 405
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5828] => Array
                        (
                            [name] => Hero_FlameDragon.Alt7
                            [cname] => Abyss Draco
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5829] => Array
                        (
                            [name] => Hero_Ellonia.Alt9
                            [cname] => Frostshard Ellonia
                            [cost] => 560
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5831] => Array
                        (
                            [name] => Hero_Tremble.Classic
                            [cname] => Throwback Tremble
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 750
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                )

            [Taunt] => Array
                (
                    [91] => Array
                        (
                            [name] => Standard
                            [cname] => Taunt
                            [cost] => 250
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [471] => Array
                        (
                            [name] => Disco_Taunt
                            [cname] => Disco Taunt
                            [cost] => 2970
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [472] => Array
                        (
                            [name] => Gore_Taunt
                            [cname] => Gore Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [522] => Array
                        (
                            [name] => Baby_Taunt
                            [cname] => Baby Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [679] => Array
                        (
                            [name] => Hellbourne_Taunt
                            [cname] => Heavy Metal Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [909] => Array
                        (
                            [name] => Fist_Taunt
                            [cname] => Fist of Sol Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [926] => Array
                        (
                            [name] => Dumpster_Taunt
                            [cname] => Dumpster Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [960] => Array
                        (
                            [name] => DroppingGs_Taunt
                            [cname] => Dropping Gs Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1002] => Array
                        (
                            [name] => Chiprel_Taunt
                            [cname] => Chiprel Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1082] => Array
                        (
                            [name] => Kongor_Taunt
                            [cname] => Kongor Taunt
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1148] => Array
                        (
                            [name] => RIP_Taunt
                            [cname] => Tombstone Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1193] => Array
                        (
                            [name] => HoneyBadger_Taunt
                            [cname] => Honey Badger Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1217] => Array
                        (
                            [name] => Acme_Taunt
                            [cname] => ACME Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1359] => Array
                        (
                            [name] => FatLady_Taunt
                            [cname] => Fat Lady Taunt
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1418] => Array
                        (
                            [name] => Blacksmith_Taunt
                            [cname] => Blacksmith Taunt
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1485] => Array
                        (
                            [name] => Celebration_Taunt
                            [cname] => Celebration Taunt
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1498] => Array
                        (
                            [name] => FortuneCookie_Taunt
                            [cname] => Fortune Cookie Taunts
                            [cost] => 450
                            [premium] => 1
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2000] => Array
                        (
                            [name] => Rainbow_Taunt
                            [cname] => Rainbow Taunt
                            [cost] => 400
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2001] => Array
                        (
                            [name] => TreasureChest_Taunt
                            [cname] => Treasure Chest Taunt
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 5000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2573] => Array
                        (
                            [name] => Ursa_Taunt
                            [cname] => URSA Taunt
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2680] => Array
                        (
                            [name] => Snowman_Taunt
                            [cname] => Snowman Taunt
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2885] => Array
                        (
                            [name] => Rest_In_P_Taunt
                            [cname] => R.I.Pepperoni Taunt
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2902] => Array
                        (
                            [name] => Gamer_Rage_Taunt
                            [cname] => 8 Bit Rage Kid Taunt
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2947] => Array
                        (
                            [name] => 5's_Taunt
                            [cname] => 5's Taunt
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3020] => Array
                        (
                            [name] => Paragon_Taunt
                            [cname] => Paragon Taunt
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3100] => Array
                        (
                            [name] => Wolf_Time_Taunt
                            [cname] => Wolf Time! Taunt
                            [cost] => 400
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3264] => Array
                        (
                            [name] => Slap_The_Troll_Taunt
                            [cname] => Slap the Troll Taunt
                            [cost] => 400
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3290] => Array
                        (
                            [name] => Siam_Taunt
                            [cname] => Siam Taunt
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3471] => Array
                        (
                            [name] => Rekt_Taunt
                            [cname] => Get REKT Taunt
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3930] => Array
                        (
                            [name] => Beam_Me_Up_Taunt
                            [cname] => Beam Me Up!
                            [cost] => 9999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3931] => Array
                        (
                            [name] => Orbital_Strike_Taunt
                            [cname] => Orbital Strike
                            [cost] => 9999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3932] => Array
                        (
                            [name] => Ascension_Boogie_Taunt
                            [cname] => Ascension Boogie
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4071] => Array
                        (
                            [name] => Killer_Ball_Taunt
                            [cname] => Killer Ball Taunt
                            [cost] => 350
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4432] => Array
                        (
                            [name] => Bad_Present_Taunt
                            [cname] => Bad Present Taunt
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4850] => Array
                        (
                            [name] => Punk_Taunt
                            [cname] => Punk Taunt
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4886] => Array
                        (
                            [name] => Miku_Taunt
                            [cname] => Miku Taunt
                            [cost] => 1999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5293] => Array
                        (
                            [name] => Songkran_Taunt
                            [cname] => Songkran Taunt
                            [cost] => 420
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5377] => Array
                        (
                            [name] => Forsaken_Taunt
                            [cname] => Shikigami
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5534] => Array
                        (
                            [name] => Poker_Taunt
                            [cname] => Poker Taunt
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                )

            [Misc] => Array
                (
                    [161] => Array
                        (
                            [name] => Nickname Change
                            [cname] => Nickname Change
                            [cost] => 1050
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [163] => Array
                        (
                            [name] => Stat Reset
                            [cname] => Stat Reset
                            [cost] => 3200
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [742] => Array
                        (
                            [name] => Elite Parasite Bundle
                            [cname] => Elite Parasite Bundle
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1792] => Array
                        (
                            [name] => Super-Taunt
                            [cname] => Super Taunt
                            [cost] => 1100
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2069] => Array
                        (
                            [name] => Dice_Bundle1
                            [cname] => Dice
                            [cost] => 5
                            [premium] => 0
                            [premium_mmp_cost] => 5
                            [dynamic] => 1
                            [local_path] => /ui/fe2/store/icons/bundle.tga
                            [purchasable] => 1
                        )

                    [2154] => Array
                        (
                            [name] => Santa's Gift Bag
                            [cname] => Santa's Gift Bag
                            [cost] => 1500
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2169] => Array
                        (
                            [name] => Stocking Stuffers
                            [cname] => Stocking Stuffers
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2240] => Array
                        (
                            [name] => eSports Footlocker
                            [cname] => eSports Footlocker
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2350] => Array
                        (
                            [name] => Vault of the Keeper
                            [cname] => Vault of the Keeper
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2351] => Array
                        (
                            [name] => Pandora's Box
                            [cname] => Pandora's Box
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2352] => Array
                        (
                            [name] => Merrick...s Mystery Box
                            [cname] => Merrick...s Mystery Box
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2511] => Array
                        (
                            [name] => Small Rift Cache
                            [cname] => Small Rift Cache
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2512] => Array
                        (
                            [name] => Large Rift Cache
                            [cname] => Large Rift Cache
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2513] => Array
                        (
                            [name] => Coffers of the Rift
                            [cname] => Coffers of the Rift
                            [cost] => 800
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2616] => Array
                        (
                            [name] => Harvest Goody Bag
                            [cname] => Harvest Goody Bag
                            [cost] => 250
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2726] => Array
                        (
                            [name] => Kongor's Stash 2014 NAEU
                            [cname] => Kongor's Stash 2014 NAEU
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2727] => Array
                        (
                            [name] => Stocking Stuffers 2014 NAEU
                            [cname] => Stocking Stuffers 2014 NAEU
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3202] => Array
                        (
                            [name] => Fun Sized Grab Bag
                            [cname] => Fun Sized Grab Bag
                            [cost] => 420
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3203] => Array
                        (
                            [name] => Full Sized Grab Bag
                            [cname] => Full Sized Grab Bag
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3246] => Array
                        (
                            [name] => King Sized Grab Bag
                            [cname] => King Sized Grab Bag
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3315] => Array
                        (
                            [name] => Loyal Customer Present
                            [cname] => Loyal Customer Present
                            [cost] => 600
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3316] => Array
                        (
                            [name] => Holiday Customer Present
                            [cname] => Holiday Customer Present
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3317] => Array
                        (
                            [name] => Vigilant Customer Present
                            [cname] => Vigilant Customer Present
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3576] => Array
                        (
                            [name] => Siam Surprise Grab Bag
                            [cname] => Siam Surprise Grab Bag
                            [cost] => 299
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3862] => Array
                        (
                            [name] => Gold Grab Bag
                            [cname] => Gold Grab Bag
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4000] => Array
                        (
                            [name] => 6th HoNiversary Goodie Bag
                            [cname] => 6th HoNiversary Goodie Bag
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4001] => Array
                        (
                            [name] => 6th HoNiversary Limited Bag
                            [cname] => 6th HoNiversary Limited Bag
                            [cost] => 350
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4002] => Array
                        (
                            [name] => 6th HoNiversary Gold Bag
                            [cname] => 6th HoNiversary Gold Bag
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4003] => Array
                        (
                            [name] => 6th HoNiversary Silver Bag
                            [cname] => 6th HoNiversary Silver Bag
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4044] => Array
                        (
                            [name] => Ascension Grab Bag 1
                            [cname] => Ascension Grab Bag 1
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4045] => Array
                        (
                            [name] => Ascension Grab Bag 2
                            [cname] => Ascension Grab Bag 2
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4046] => Array
                        (
                            [name] => LE & HE Grab Bag
                            [cname] => LE & HE Grab Bag
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4047] => Array
                        (
                            [name] => Gold Collection Grab Bag
                            [cname] => Gold Collection Grab Bag
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4048] => Array
                        (
                            [name] => Ascension Grab Bag Voucher
                            [cname] => Ascension Grab Bag Voucher
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4146] => Array
                        (
                            [name] => Backpack 1
                            [cname] => Backpack 1
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4147] => Array
                        (
                            [name] => Backpack 2
                            [cname] => Backpack 2
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 1250
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4148] => Array
                        (
                            [name] => Backpack 3
                            [cname] => Backpack 3
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4149] => Array
                        (
                            [name] => Backpack 4
                            [cname] => Backpack 4
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4150] => Array
                        (
                            [name] => Backpack 5
                            [cname] => Backpack 5
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4605] => Array
                        (
                            [name] => Super boost
                            [cname] => Super boost
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                )

            [Alt Announcement] => Array
                (
                    [164] => Array
                        (
                            [name] => Flamboyant
                            [cname] => Flamboyant Pack
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [235] => Array
                        (
                            [name] => Female
                            [cname] => Pudding Pack
                            [cost] => 900
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [410] => Array
                        (
                            [name] => Badass
                            [cname] => Badass Pack
                            [cost] => 600
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [664] => Array
                        (
                            [name] => British
                            [cname] => British Gentleman Pack
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [890] => Array
                        (
                            [name] => BreakyCPK
                            [cname] => BreakyCPK Pack
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1059] => Array
                        (
                            [name] => Pimp
                            [cname] => Pimp Pack
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1311] => Array
                        (
                            [name] => Seductive
                            [cname] => Seductive Pack
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1522] => Array
                        (
                            [name] => Thai
                            [cname] => VRZO Thai Announcer
                            [cost] => 600
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1523] => Array
                        (
                            [name] => Thai English
                            [cname] => VRZO English Announcer
                            [cost] => 600
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1999] => Array
                        (
                            [name] => Pirate Announcer
                            [cname] => Pirate Announcer
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2031] => Array
                        (
                            [name] => Samuel L Jackson
                            [cname] => Samuel L. Jackson Pack
                            [cost] => 1300
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2108] => Array
                        (
                            [name] => Censored Samuel L Jackson
                            [cname] => Samuel L. Jackson Pack
                            [cost] => 1300
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2316] => Array
                        (
                            [name] => Na Khom Thai Announcer
                            [cname] => Na Khom Thai Announcer
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2339] => Array
                        (
                            [name] => Ninja Announcer Pack
                            [cname] => Ninja Announcer Pack
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2627] => Array
                        (
                            [name] => URSA Corps Announcer Pack
                            [cname] => URSA Corps Announcer Pack
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2852] => Array
                        (
                            [name] => Merrick Announcer Pack
                            [cname] => Merrick Announcer Pack
                            [cost] => 1200
                            [premium] => 1
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2905] => Array
                        (
                            [name] => 8-Bit Announcer Pack
                            [cname] => 8-Bit Announcer Pack
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2934] => Array
                        (
                            [name] => South East Asia Pack
                            [cname] => South East Asia Pack
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3014] => Array
                        (
                            [name] => Surfer Announcer Pack
                            [cname] => Surfer Announcer Pack
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3021] => Array
                        (
                            [name] => Paragon Announcer Pack
                            [cname] => Paragon Announcer Pack
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3153] => Array
                        (
                            [name] => Dark Master Announcer Pack
                            [cname] => Dark Master Announcer Pack
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3318] => Array
                        (
                            [name] => Siam Warrior Announcer Pack
                            [cname] => Siam Warrior Announcer Pack
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3939] => Array
                        (
                            [name] => Ascension Announcer Pack
                            [cname] => Ascension Announcer
                            [cost] => 1500
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4037] => Array
                        (
                            [name] => SoccerAnnouncerPack
                            [cname] => Soccer Announcer Pack
                            [cost] => 300
                            [premium] => 1
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4186] => Array
                        (
                            [name] => Haunted House Announcer
                            [cname] => Haunted House Announcer
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4437] => Array
                        (
                            [name] => Miku Announcer
                            [cname] => Miku Announcer
                            [cost] => 975
                            [premium] => 1
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4450] => Array
                        (
                            [name] => MsPudding
                            [cname] => Return of MsPudding
                            [cost] => 600
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4849] => Array
                        (
                            [name] => Punk Announcer
                            [cname] => Punk Announcer
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4911] => Array
                        (
                            [name] => ESan Announcer Pack
                            [cname] => E-San Announcer
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5457] => Array
                        (
                            [name] => 2018 World Cup Announcer
                            [cname] => 2018 World Cup Announcer
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                )

            [Couriers] => Array
                (
                    [462] => Array
                        (
                            [name] => penguin_courier
                            [cname] => Penguin Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [463] => Array
                        (
                            [name] => whelp_courier
                            [cname] => Whelp Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [485] => Array
                        (
                            [name] => chicken_courier
                            [cname] => Chicken Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [486] => Array
                        (
                            [name] => goblin_courier
                            [cname] => Goblin Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [487] => Array
                        (
                            [name] => pig_courier
                            [cname] => Pig Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [488] => Array
                        (
                            [name] => bat_courier
                            [cname] => Bat Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [489] => Array
                        (
                            [name] => robot_courier
                            [cname] => Robot Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [709] => Array
                        (
                            [name] => cat_courier
                            [cname] => Nyan Cat Courier
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [951] => Array
                        (
                            [name] => dino_courier
                            [cname] => Dino Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [958] => Array
                        (
                            [name] => bernard_courier
                            [cname] => St. Bernard Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [959] => Array
                        (
                            [name] => panda_courier
                            [cname] => Panda Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1083] => Array
                        (
                            [name] => kongor_courier
                            [cname] => Kongor Kourier
                            [cost] => 300
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1191] => Array
                        (
                            [name] => honeybadger_courier
                            [cname] => Honey Badger Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1192] => Array
                        (
                            [name] => garena_courier
                            [cname] => Garena Courier
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 15000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1199] => Array
                        (
                            [name] => hamster_courier
                            [cname] => Hamster Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1406] => Array
                        (
                            [name] => caterpillar_courier
                            [cname] => Caterpillar Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [1437] => Array
                        (
                            [name] => turkey_courier
                            [cname] => Turkey Courier
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2361] => Array
                        (
                            [name] => izbushka_courier
                            [cname] => Izbushka Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2428] => Array
                        (
                            [name] => cheburashka_courier
                            [cname] => Cheburashka Courier
                            [cost] => 400
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2572] => Array
                        (
                            [name] => ursa_courier
                            [cname] => URSA Courier
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2615] => Array
                        (
                            [name] => pumpkin_courier
                            [cname] => Pumpkin Courier
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2766] => Array
                        (
                            [name] => sheep_courier
                            [cname] => Sheep Courier
                            [cost] => 450
                            [premium] => 0
                            [premium_mmp_cost] => 3500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2814] => Array
                        (
                            [name] => postman_courier
                            [cname] => GSL Postman Courier
                            [cost] => 400
                            [premium] => 1
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2866] => Array
                        (
                            [name] => 8bit_courier
                            [cname] => 8 Bit Courier
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2910] => Array
                        (
                            [name] => wareffort_courier
                            [cname] => Gnome Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 400
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3019] => Array
                        (
                            [name] => paragon_courier
                            [cname] => Paragon Courier
                            [cost] => 1500
                            [premium] => 1
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3288] => Array
                        (
                            [name] => fairy_courier
                            [cname] => Fairy Courier
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3510] => Array
                        (
                            [name] => dragon_stage_1_courier
                            [cname] => Dragon Courier Stage 1
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3511] => Array
                        (
                            [name] => dragon_stage_2_courier
                            [cname] => Dragon Courier Stage 2
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3512] => Array
                        (
                            [name] => dragon_stage_3_courier
                            [cname] => Dragon Courier Stage 3
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3513] => Array
                        (
                            [name] => dragon_stage_4_courier
                            [cname] => Dragon Courier Stage 4
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3514] => Array
                        (
                            [name] => dragon_stage_5_courier
                            [cname] => Dragon Courier Stage 5
                            [cost] => 1000
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3515] => Array
                        (
                            [name] => dragon_courier_stage6
                            [cname] => Dragon Courier Stage 6
                            [cost] => 1000
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3936] => Array
                        (
                            [name] => ascension_hyperdrive_courier
                            [cname] => Hyperdrive courier
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3937] => Array
                        (
                            [name] => ascension_gizmo_courier
                            [cname] => Gizmo courier
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3938] => Array
                        (
                            [name] => ascension_drone_courier
                            [cname] => Drone courier
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4068] => Array
                        (
                            [name] => streaker_courier
                            [cname] => Streaker Courier
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 2000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4109] => Array
                        (
                            [name] => gryphon_courier
                            [cname] => Gryphon Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4116] => Array
                        (
                            [name] => demon_courier
                            [cname] => Demon Courier
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4431] => Array
                        (
                            [name] => reindeer_courier
                            [cname] => Flying Reindeer
                            [cost] => 420
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4847] => Array
                        (
                            [name] => punk_courier
                            [cname] => Punk Courier
                            [cost] => 900
                            [premium] => 0
                            [premium_mmp_cost] => 4000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                )

            [Hero] => Array
                (
                    [572] => Array
                        (
                            [name] => Hero_Armadon.Hero
                            [cname] => Armadon
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [573] => Array
                        (
                            [name] => Hero_Behemoth.Hero
                            [cname] => Behemoth
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [574] => Array
                        (
                            [name] => Hero_Chronos.Hero
                            [cname] => Chronos
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [575] => Array
                        (
                            [name] => Hero_Defiler.Hero
                            [cname] => Defiler
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [576] => Array
                        (
                            [name] => Hero_Devourer.Hero
                            [cname] => Devourer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [577] => Array
                        (
                            [name] => Hero_DwarfMagi.Hero
                            [cname] => Blacksmith
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [578] => Array
                        (
                            [name] => Hero_Ebulus.Hero
                            [cname] => Slither
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [579] => Array
                        (
                            [name] => Hero_Electrician.Hero
                            [cname] => Electrician
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [580] => Array
                        (
                            [name] => Hero_Fairy.Hero
                            [cname] => Nymphora
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [581] => Array
                        (
                            [name] => Hero_Frosty.Hero
                            [cname] => Glacius
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [582] => Array
                        (
                            [name] => Hero_Hammerstorm.Hero
                            [cname] => Hammerstorm
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [583] => Array
                        (
                            [name] => Hero_Hantumon.Hero
                            [cname] => Night Hound
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [584] => Array
                        (
                            [name] => Hero_Hiro.Hero
                            [cname] => Swiftblade
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [585] => Array
                        (
                            [name] => Hero_Hunter.Hero
                            [cname] => Blood Hunter
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [586] => Array
                        (
                            [name] => Hero_Kraken.Hero
                            [cname] => Kraken
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [587] => Array
                        (
                            [name] => Hero_Kunas.Hero
                            [cname] => Thunderbringer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [588] => Array
                        (
                            [name] => Hero_Krixi.Hero
                            [cname] => Moon Queen
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [589] => Array
                        (
                            [name] => Hero_PollywogPriest.Hero
                            [cname] => Pollywog Priest
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [590] => Array
                        (
                            [name] => Hero_Rocky.Hero
                            [cname] => Pebbles
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [591] => Array
                        (
                            [name] => Hero_Soulstealer.Hero
                            [cname] => Soulstealer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [592] => Array
                        (
                            [name] => Hero_Treant.Hero
                            [cname] => Keeper of the Forest
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [593] => Array
                        (
                            [name] => Hero_Vanya.Hero
                            [cname] => The Dark Lady
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [594] => Array
                        (
                            [name] => Hero_Shaman.Hero
                            [cname] => Demented Shaman
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [595] => Array
                        (
                            [name] => Hero_Voodoo.Hero
                            [cname] => Voodoo Jester
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [596] => Array
                        (
                            [name] => Hero_WolfMan.Hero
                            [cname] => War Beast
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [597] => Array
                        (
                            [name] => Hero_Yogi.Hero
                            [cname] => Wild Soul
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [598] => Array
                        (
                            [name] => Hero_Zephyr.Hero
                            [cname] => Zephyr
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [599] => Array
                        (
                            [name] => Hero_Mumra.Hero
                            [cname] => Pharaoh
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [600] => Array
                        (
                            [name] => Hero_Tempest.Hero
                            [cname] => Tempest
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [601] => Array
                        (
                            [name] => Hero_Ophelia.Hero
                            [cname] => Ophelia
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [602] => Array
                        (
                            [name] => Hero_Moraxus.Hero
                            [cname] => Moraxus
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [603] => Array
                        (
                            [name] => Hero_Javaras.Hero
                            [cname] => Magebane
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [604] => Array
                        (
                            [name] => Hero_Legionnaire.Hero
                            [cname] => Legionnaire
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [605] => Array
                        (
                            [name] => Hero_Predator.Hero
                            [cname] => Predator
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [606] => Array
                        (
                            [name] => Hero_Accursed.Hero
                            [cname] => Accursed
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [607] => Array
                        (
                            [name] => Hero_Nomad.Hero
                            [cname] => Nomad
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [608] => Array
                        (
                            [name] => Hero_Scar.Hero
                            [cname] => The Madman
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [609] => Array
                        (
                            [name] => Hero_Scout.Hero
                            [cname] => Scout
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [610] => Array
                        (
                            [name] => Hero_Pyromancer.Hero
                            [cname] => Pyromancer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [611] => Array
                        (
                            [name] => Hero_PuppetMaster.Hero
                            [cname] => Puppet Master
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [612] => Array
                        (
                            [name] => Hero_Pestilence.Hero
                            [cname] => Pestilence
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [613] => Array
                        (
                            [name] => Hero_Maliken.Hero
                            [cname] => Maliken
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [614] => Array
                        (
                            [name] => Hero_Arachna.Hero
                            [cname] => Arachna
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [615] => Array
                        (
                            [name] => Hero_Hellbringer.Hero
                            [cname] => Hellbringer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [616] => Array
                        (
                            [name] => Hero_Xalynx.Hero
                            [cname] => Torturer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [617] => Array
                        (
                            [name] => Hero_Jereziah.Hero
                            [cname] => Jeraziah
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [618] => Array
                        (
                            [name] => Hero_Andromeda.Hero
                            [cname] => Andromeda
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [619] => Array
                        (
                            [name] => Hero_Valkyrie.Hero
                            [cname] => Valkyrie
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [620] => Array
                        (
                            [name] => Hero_BabaYaga.Hero
                            [cname] => Wretched Hag
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [621] => Array
                        (
                            [name] => Hero_Succubis.Hero
                            [cname] => Succubus
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [622] => Array
                        (
                            [name] => Hero_Magmar.Hero
                            [cname] => Magmus
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [623] => Array
                        (
                            [name] => Hero_DiseasedRider.Hero
                            [cname] => Plague Rider
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [624] => Array
                        (
                            [name] => Hero_HellDemon.Hero
                            [cname] => Soul Reaper
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [625] => Array
                        (
                            [name] => Hero_Panda.Hero
                            [cname] => Pandamonium
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [626] => Array
                        (
                            [name] => Hero_Vindicator.Hero
                            [cname] => Vindicator
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [627] => Array
                        (
                            [name] => Hero_CorruptedDisciple.Hero
                            [cname] => Corrupted Disciple
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [628] => Array
                        (
                            [name] => Hero_SandWraith.Hero
                            [cname] => Sand Wraith
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [629] => Array
                        (
                            [name] => Hero_Rampage.Hero
                            [cname] => Rampage
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [630] => Array
                        (
                            [name] => Hero_WitchSlayer.Hero
                            [cname] => Witch Slayer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [631] => Array
                        (
                            [name] => Hero_ForsakenArcher.Hero
                            [cname] => Forsaken Archer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [632] => Array
                        (
                            [name] => Hero_Engineer.Hero
                            [cname] => Engineer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [633] => Array
                        (
                            [name] => Hero_Deadwood.Hero
                            [cname] => Deadwood
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [634] => Array
                        (
                            [name] => Hero_Chipper.Hero
                            [cname] => The Chipper
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [635] => Array
                        (
                            [name] => Hero_Bubbles.Hero
                            [cname] => Bubbles
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [636] => Array
                        (
                            [name] => Hero_Fade.Hero
                            [cname] => Fayde
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [637] => Array
                        (
                            [name] => Hero_Bephelgor.Hero
                            [cname] => Balphagore
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [638] => Array
                        (
                            [name] => Hero_Gauntlet.Hero
                            [cname] => Gauntlet
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [639] => Array
                        (
                            [name] => Hero_Tundra.Hero
                            [cname] => Tundra
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [640] => Array
                        (
                            [name] => Hero_Gladiator.Hero
                            [cname] => The Gladiator
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [641] => Array
                        (
                            [name] => Hero_DoctorRepulsor.Hero
                            [cname] => Doctor Repulsor
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [642] => Array
                        (
                            [name] => Hero_Tremble.Hero
                            [cname] => Tremble
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [643] => Array
                        (
                            [name] => Hero_FlintBeastwood.Hero
                            [cname] => Flint Beastwood
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [644] => Array
                        (
                            [name] => Hero_Bombardier.Hero
                            [cname] => Bombardier
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [645] => Array
                        (
                            [name] => Hero_Hydromancer.Hero
                            [cname] => Myrmidon
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [646] => Array
                        (
                            [name] => Hero_Dampeer.Hero
                            [cname] => Dampeer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [647] => Array
                        (
                            [name] => Hero_Empath.Hero
                            [cname] => Empath
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [648] => Array
                        (
                            [name] => Hero_Aluna.Hero
                            [cname] => Aluna
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [649] => Array
                        (
                            [name] => Hero_Silhouette.Hero
                            [cname] => Silhouette
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [650] => Array
                        (
                            [name] => Hero_Flux.Hero
                            [cname] => Flux
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [651] => Array
                        (
                            [name] => Hero_Martyr.Hero
                            [cname] => Martyr
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [652] => Array
                        (
                            [name] => Hero_Ra.Hero
                            [cname] => Amun Ra
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [653] => Array
                        (
                            [name] => Hero_Parasite.Hero
                            [cname] => Parasite
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [654] => Array
                        (
                            [name] => Hero_EmeraldWarden.Hero
                            [cname] => Emerald Warden
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [665] => Array
                        (
                            [name] => Hero_MonkeyKing.Hero
                            [cname] => Monkey King
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [666] => Array
                        (
                            [name] => Hero_DrunkenMaster.Hero
                            [cname] => Drunken Master
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [667] => Array
                        (
                            [name] => Hero_Revenant.Hero
                            [cname] => Revenant
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [694] => Array
                        (
                            [name] => Hero_MasterOfArms.Hero
                            [cname] => Master of Arms
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [700] => Array
                        (
                            [name] => Hero_Rhapsody.Hero
                            [cname] => Rhapsody
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [751] => Array
                        (
                            [name] => Hero_Geomancer.Hero
                            [cname] => Geomancer
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [837] => Array
                        (
                            [name] => Hero_Midas.Hero
                            [cname] => Midas
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [847] => Array
                        (
                            [name] => Hero_Cthulhuphant.Hero
                            [cname] => Cthulhuphant
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [859] => Array
                        (
                            [name] => Hero_Monarch.Hero
                            [cname] => Monarch
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [871] => Array
                        (
                            [name] => Hero_Gemini.Hero
                            [cname] => Gemini
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [893] => Array
                        (
                            [name] => Hero_Dreadknight.Hero
                            [cname] => Lord Salforis
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [904] => Array
                        (
                            [name] => Hero_ShadowBlade.Hero
                            [cname] => Shadowblade
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [930] => Array
                        (
                            [name] => Hero_Artesia.Hero
                            [cname] => Artesia
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [943] => Array
                        (
                            [name] => Hero_Taint.Hero
                            [cname] => Gravekeeper
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [971] => Array
                        (
                            [name] => Hero_Berzerker.Hero
                            [cname] => Berzerker
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [996] => Array
                        (
                            [name] => Hero_FlameDragon.Hero
                            [cname] => Draconis
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1005] => Array
                        (
                            [name] => Hero_Kenisis.Hero
                            [cname] => Kinesis
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1015] => Array
                        (
                            [name] => Hero_Gunblade.Hero
                            [cname] => Gunblade
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1027] => Array
                        (
                            [name] => Hero_Blitz.Hero
                            [cname] => Blitz
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1055] => Array
                        (
                            [name] => Hero_Artillery.Hero
                            [cname] => Artillery
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1062] => Array
                        (
                            [name] => Hero_Ellonia.Hero
                            [cname] => Ellonia
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1140] => Array
                        (
                            [name] => Hero_Riftmage.Hero
                            [cname] => Riftwalker
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1151] => Array
                        (
                            [name] => Hero_Plant.Hero
                            [cname] => Bramble
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1164] => Array
                        (
                            [name] => Hero_Ravenor.Hero
                            [cname] => Ravenor
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1205] => Array
                        (
                            [name] => Hero_Prophet.Hero
                            [cname] => Prophet
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1223] => Array
                        (
                            [name] => Hero_Rally.Hero
                            [cname] => Rally
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1262] => Array
                        (
                            [name] => AllHeroes.Hero
                            [cname] => All Heroes
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1294] => Array
                        (
                            [name] => Hero_Oogie.Hero
                            [cname] => Oogie
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1337] => Array
                        (
                            [name] => Hero_Solstice.Hero
                            [cname] => Solstice
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1385] => Array
                        (
                            [name] => Hero_Pearl.Hero
                            [cname] => Pearl
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1428] => Array
                        (
                            [name] => Hero_Grinex.Hero
                            [cname] => Grinex
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1458] => Array
                        (
                            [name] => Hero_Lodestone.Hero
                            [cname] => Lodestone
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1517] => Array
                        (
                            [name] => Hero_Bushwack.Hero
                            [cname] => Bushwack
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1587] => Array
                        (
                            [name] => Hero_Salomon.Hero
                            [cname] => Salomon
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1612] => Array
                        (
                            [name] => Hero_Prisoner.Hero
                            [cname] => Prisoner 945
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1696] => Array
                        (
                            [name] => Hero_SirBenzington.Hero
                            [cname] => Sir Benzington
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [1993] => Array
                        (
                            [name] => Hero_Circe.Hero
                            [cname] => Circe the Deceiver
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2109] => Array
                        (
                            [name] => Hero_Klanx.Hero
                            [cname] => Klanx
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2219] => Array
                        (
                            [name] => Hero_Moira.Hero
                            [cname] => Moira
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2263] => Array
                        (
                            [name] => Hero_Riptide.Hero
                            [cname] => Riptide
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2379] => Array
                        (
                            [name] => Hero_Tarot.Hero
                            [cname] => Tarot
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2777] => Array
                        (
                            [name] => Hero_Deadlift.Hero
                            [cname] => Deadlift
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3337] => Array
                        (
                            [name] => Hero_KingKlout.Hero
                            [cname] => King Klout
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3897] => Array
                        (
                            [name] => Hero_Shellshock.Hero
                            [cname] => Shellshock
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4095] => Array
                        (
                            [name] => Hero_Ichor.Hero
                            [cname] => Ichor
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4753] => Array
                        (
                            [name] => Hero_Warchief.Hero
                            [cname] => Warchief
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4944] => Array
                        (
                            [name] => Hero_Sapphire.Hero
                            [cname] => Sapphire
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5168] => Array
                        (
                            [name] => Hero_Goldenveil.Hero
                            [cname] => Goldenveil
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 9002
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [5346] => Array
                        (
                            [name] => Hero_Chi.Hero
                            [cname] => Chi
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [5511] => Array
                        (
                            [name] => Hero_Mimix.Hero
                            [cname] => Mimix
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                )

            [Ward] => Array
                (
                    [2916] => Array
                        (
                            [name] => sir_benzington_ward
                            [cname] => Sir Benzington Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2665] => Array
                        (
                            [name] => aluna_ward
                            [cname] => Aluna Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2666] => Array
                        (
                            [name] => empath_ward
                            [cname] => Empath Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2669] => Array
                        (
                            [name] => glacius_ward
                            [cname] => Glacius Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2670] => Array
                        (
                            [name] => pearl_ward
                            [cname] => Pearl Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2671] => Array
                        (
                            [name] => rhapsody_ward
                            [cname] => Rhapsody Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2672] => Array
                        (
                            [name] => torturer_ward
                            [cname] => Torturer Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2673] => Array
                        (
                            [name] => ursa_ward
                            [cname] => URSA Ward
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2687] => Array
                        (
                            [name] => christmas_ward
                            [cname] => Christmas Tree Ward
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2688] => Array
                        (
                            [name] => menorah_ward
                            [cname] => Menorah Ward
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2689] => Array
                        (
                            [name] => calamity_ward
                            [cname] => Calamity Ward
                            [cost] => 0
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2691] => Array
                        (
                            [name] => cassie_ward
                            [cname] => Cassie Ward
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3593] => Array
                        (
                            [name] => easter_ward
                            [cname] => Easter Egg Ward
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2786] => Array
                        (
                            [name] => tempest_ward
                            [cname] => Tempest Ward
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2787] => Array
                        (
                            [name] => keeper_ward
                            [cname] => Keeper of the Forest Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2788] => Array
                        (
                            [name] => parasite_ward
                            [cname] => Parasite Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2789] => Array
                        (
                            [name] => ophelia_ward
                            [cname] => Ophelia Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2790] => Array
                        (
                            [name] => solstice_ward
                            [cname] => Solstice Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2791] => Array
                        (
                            [name] => warbeast_ward
                            [cname] => War Beast Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2792] => Array
                        (
                            [name] => cthulhuphant_ward
                            [cname] => Cthulhuphant Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2793] => Array
                        (
                            [name] => deadlift_ward
                            [cname] => Deadlift Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2800] => Array
                        (
                            [name] => shamrock_ward
                            [cname] => Shamrock Ward
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2816] => Array
                        (
                            [name] => gsl_ward
                            [cname] => GSL Ward
                            [cost] => 300
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2843] => Array
                        (
                            [name] => ddog_ward
                            [cname] => DDog Ward
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2844] => Array
                        (
                            [name] => sync_ward
                            [cname] => Sync Ward
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2849] => Array
                        (
                            [name] => 8bit_ward
                            [cname] => 8-Bit Ward
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2853] => Array
                        (
                            [name] => honiversary_5_ward
                            [cname] => Honiversary 5 Ward
                            [cost] => 300
                            [premium] => 1
                            [premium_mmp_cost] => 600
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2859] => Array
                        (
                            [name] => magebane_ward
                            [cname] => Magebane Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2860] => Array
                        (
                            [name] => silhouette_ward
                            [cname] => Silhouette Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2861] => Array
                        (
                            [name] => darklady_ward
                            [cname] => The Dark Lady Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2862] => Array
                        (
                            [name] => moonqueen_ward
                            [cname] => Moon Queen Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2863] => Array
                        (
                            [name] => swiftblade_ward
                            [cname] => Swiftblade Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2864] => Array
                        (
                            [name] => forsaken_archer_ward
                            [cname] => Forsaken Archer Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2909] => Array
                        (
                            [name] => war_effort_ward
                            [cname] => Dragon's Treasure Ward
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 800
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [2917] => Array
                        (
                            [name] => pharaoh_ward
                            [cname] => Pharaoh Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2918] => Array
                        (
                            [name] => pebbles_ward
                            [cname] => Pebbles Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2919] => Array
                        (
                            [name] => hammerstorm_ward
                            [cname] => Hammerstorm Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2920] => Array
                        (
                            [name] => fayde_ward
                            [cname] => Fayde Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2921] => Array
                        (
                            [name] => magmus_ward
                            [cname] => Magmus Ward
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2997] => Array
                        (
                            [name] => independence_day_ward
                            [cname] => Independence Day Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1000
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [2998] => Array
                        (
                            [name] => pelita_ward
                            [cname] => Pelita Ward
                            [cost] => 100
                            [premium] => 0
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3018] => Array
                        (
                            [name] => paragon_ward
                            [cname] => Paragon Ward
                            [cost] => 0
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3048] => Array
                        (
                            [name] => deadwood_ward
                            [cname] => Deadwood Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3049] => Array
                        (
                            [name] => devourer_ward
                            [cname] => Devourer Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3050] => Array
                        (
                            [name] => kraken_ward
                            [cname] => Kraken Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3051] => Array
                        (
                            [name] => gauntlet_ward
                            [cname] => Gauntlet Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3052] => Array
                        (
                            [name] => nomad_ward
                            [cname] => Nomad Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3053] => Array
                        (
                            [name] => ravenor_ward
                            [cname] => Ravenor Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3055] => Array
                        (
                            [name] => beach_ball_ward
                            [cname] => Beach Ball Ward
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3147] => Array
                        (
                            [name] => bubbles_ward
                            [cname] => Bubbles Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3148] => Array
                        (
                            [name] => chronos_ward
                            [cname] => Chronos Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3149] => Array
                        (
                            [name] => wildsoul_ward
                            [cname] => Wildsoul Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3150] => Array
                        (
                            [name] => plague_rider_ward
                            [cname] => Plague Rider Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3151] => Array
                        (
                            [name] => rally_ward
                            [cname] => Rally Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3152] => Array
                        (
                            [name] => wretched_hag_ward
                            [cname] => Wretched Hag Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3204] => Array
                        (
                            [name] => devo_paku_ward
                            [cname] => Paku Devourer Ward
                            [cost] => 300
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3205] => Array
                        (
                            [name] => devo_pirate_ward
                            [cname] => Captain Gorebeard Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3206] => Array
                        (
                            [name] => bedsheet_devo_ward
                            [cname] => Bedsheet Devourer Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3207] => Array
                        (
                            [name] => jinchan_devo_ward
                            [cname] => Jin Chan Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3217] => Array
                        (
                            [name] => rift_devo_ward
                            [cname] => Rift Devourer Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3218] => Array
                        (
                            [name] => gluttony_devo_ward
                            [cname] => Gluttony Devourer Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3219] => Array
                        (
                            [name] => halloween_ward
                            [cname] => Halloween Ward
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3245] => Array
                        (
                            [name] => hotshot_heroes_ward
                            [cname] => Hotshot Heroes Ward
                            [cost] => 390
                            [premium] => 1
                            [premium_mmp_cost] => 2500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3272] => Array
                        (
                            [name] => siam_ward
                            [cname] => Siam Warrior Ward
                            [cost] => 400
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3289] => Array
                        (
                            [name] => thanksgiving_ward
                            [cname] => Thanksgiving Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3313] => Array
                        (
                            [name] => christmas_2015_ward
                            [cname] => Christmas 2015 Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3314] => Array
                        (
                            [name] => new_year_2016_ward
                            [cname] => New Year 2016 Ward
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3466] => Array
                        (
                            [name] => chinese_ny_2016_ward
                            [cname] => Chinese New Year 2016 Ward
                            [cost] => 200
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3495] => Array
                        (
                            [name] => valentines_2016_ward
                            [cname] => Valentine's Day Ward 2016
                            [cost] => 200
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [3933] => Array
                        (
                            [name] => lookout_ward
                            [cname] => Lookout Ward
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3934] => Array
                        (
                            [name] => vizmo_ward
                            [cname] => Vizmo Ward
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [3935] => Array
                        (
                            [name] => sentry_ward
                            [cname] => Sentry Ward
                            [cost] => 2000
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4069] => Array
                        (
                            [name] => floodlight_ward
                            [cname] => Floodlight Ward
                            [cost] => 150
                            [premium] => 1
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4070] => Array
                        (
                            [name] => penalty_card_ward
                            [cname] => Penalty Card Ward
                            [cost] => 150
                            [premium] => 0
                            [premium_mmp_cost] => 1500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4429] => Array
                        (
                            [name] => bigeye_ward
                            [cname] => Christmas Monster
                            [cost] => 420
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4430] => Array
                        (
                            [name] => snowman_ward
                            [cname] => Snowman
                            [cost] => 420
                            [premium] => 0
                            [premium_mmp_cost] => 3000
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4848] => Array
                        (
                            [name] => punk_ward
                            [cname] => Punk Ward
                            [cost] => 500
                            [premium] => 0
                            [premium_mmp_cost] => 4500
                            [dynamic] => 0
                            [purchasable] => 1
                        )

                    [4885] => Array
                        (
                            [name] => miku_ward
                            [cname] => Miku Ward
                            [cost] => 999
                            [premium] => 0
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                )

            [EAP] => Array
                (
                    [4110] => Array
                        (
                            [name] => Hero_Ichor.eap
                            [cname] => Ichor
                            [cost] => 300
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4111] => Array
                        (
                            [name] => Hero_Ichor.Alt
                            [cname] => Ichor Legendary Bundle
                            [cost] => 500
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                    [4112] => Array
                        (
                            [name] => Hero_Ichor.Alt2
                            [cname] => Ichor Immortal Bundle
                            [cost] => 650
                            [premium] => 1
                            [premium_mmp_cost] => 0
                            [dynamic] => 0
                            [purchasable] => 0
                        )

                )

        )

    [crc] => 2356729933
    [vested_threshold] => 5
    [0] => 1
)
```