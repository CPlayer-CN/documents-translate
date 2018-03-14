**编辑时间**  
2018年3月14日17:41:37 - 2018年3月14日17:46:29 | 原文部分编辑完成  

**原文链接**

---
# 译文

# 原文
Here I show a ranks example that was created by [@clip](https://www.spigotmc.org/members/1001/) and I am now bringing it live (with a few modest changes). This ranks gui requires EZRanksPro in order to function properly, of course you can still edit what you need to. Hope you enjoy.

To make this work fine you have to download [PlaceholdersAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) and download the Player, EzRanksPro expansions using:
```
/papi ecloud download Player
/papi ecloud download EzRanksPro
```

**DeluxeMenus - 1.9.2**
```yaml
 ranks:
    menu_title: '&aRanks'
    open_command:
   - ranks
    - rank
    size: 9
    items:
      A-COMPLETE:
        material: WOOL
        data: 7
        amount: 1
        slot: 0
        priority: 1
        view_requirement: BukkitPlayer.hasPermission("ezranks.rank.B");
        display_name: '&aA &7- &aComplete'
        lore:
        - '&7Cost: &fFree'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp A'
      A-CURRENT-RANK:
        material: WOOL
        data: 13
        amount: 1
        slot: 0
        priority: 2
        view_requirement: '"%ezrankspro_rank%".equals("A");'
        display_name: '&aA &7- &aCurrent rank'
        lore:
        - '&7Cost: &fFree'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp A'
      B-COMPLETE:
        material: WOOL
        data: 7
        amount: 2
        slot: 1
        priority: 1
        view_requirement: BukkitPlayer.hasPermission("ezranks.rank.C");
        display_name: '&bB &7- &aComplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp B'
      B-CURRENT-RANK:
        material: WOOL
        data: 13
        amount: 2
        slot: 1
        priority: 2
        view_requirement: '"%ezrankspro_rank%".equals("B");'
        display_name: '&bB &7- &aCurrent rank'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp B'
      B-NEXT-RANK:
        material: WOOL
        data: 8
        slot: 1
        priority: 3
        view_requirement: '"ezrankspro_rank%".equals("A");'
        display_name: '&bB &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a%ezrankspro_progress%&f%'
        click_commands:
       - '[close]'
        - '[player] warp B'
      B:
        material: WOOL
        data: 8
        amount: 2
        slot: 1
        priority: 3
        display_name: '&bB &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &cLOCKED'
        click_commands:
       - '[close]'
        - '[player] warp B'
      C-COMPLETE:
        material: WOOL
        data: 7
        amount: 3
        slot: 2
        priority: 1
        view_requirement: BukkitPlayer.hasPermission("ezranks.rank.D");
        display_name: '&cC &7- &aComplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp C'
      C-CURRENT-RANK:
        material: WOOL
        data: 13
        amount: 3
        slot: 2
        priority: 2
        view_requirement: '"%ezrankspro_rank%".equals("C");'
        display_name: '&cC &7- &aCurrent rank'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a100&f%'
        click_commands:
       - '[close]'
        - '[player] warp C'
      C-NEXT-RANK:
        material: WOOL
        data: 8
        slot: 1
        priority: 3
        view_requirement: '"ezrankspro_rank%".equals("B");'
        display_name: '&cC &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a%ezrankspro_progress%&f%'
        click_commands:
       - '[close]'
        - '[player] warp C'
      C:
        material: WOOL
        data: 8
        amount: 3
        slot: 2
        priority: 3
        display_name: '&cC &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &cLOCKED'
        click_commands:
       - '[close]'
        - '[player] warp C'
```

**DeluxeMenus - 1.10.0**
```yaml
 ranks:
    menu_title: '&8Ranks'
    open_command:
   - ranks
    - rank
    size: 9
    items:
      A-COMPLETE:
        material: WOOL
        data: 7
        slot: 0
        priority: 1
        view_requirement:
          requirements:
            complete:
              type: string equals
              input: '%player_has_permission_ezranks.rank.B%'
              output: 'yes'
        display_name: '&aA &7- &aComplete'
        lore:
        - '&7Cost: &fFree'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp A'
        right_click_commands:
       - '[close]'
        - '[player] warp A'
      A-CURRENT-RANK:
        material: WOOL
        data: 13
        slot: 0
        priority: 2
        view_requirement:
          requirements:
            complete:
              type: string equals ignorecase
              input: '%ezrankspro_rank%'
              output: A
        display_name: '&aA &7- &aCurrent rank'
        lore:
        - '&7Cost: &fFree'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp A'
        right_click_commands:
       - '[close]'
        - '[player] warp A'
      B-COMPLETE:
        material: WOOL
        data: 7
        slot: 1
        priority: 1
        view_requirement:
          requirements:
            complete:
              type: string equals
              input: '%player_has_permission_ezranks.rank.c%'
              output: 'yes'
        display_name: '&bB &7- &aComplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp B'
        right_click_commands:
       - '[close]'
        - '[player] warp B'
      B-CURRENT-RANK:
        material: WOOL
        data: 13
        slot: 1
        priority: 2
        view_requirement:
          requirements:
            complete:
              type: string equals ignorecase
              input: '%ezrankspro_rank%'
              output: B
        display_name: '&bB &7- &aCurrent rank'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp B'
        right_click_commands:
       - '[close]'
        - '[player] warp B'
      B-NEXT-RANK:
        material: WOOL
        data: 8
        slot: 1
        priority: 3
        view_requirement:
          requirements:
            complete:
              type: string equals ignorecase
              input: '%ezrankspro_rank%'
              output: A
        display_name: '&bB &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &a%ezrankspro_progress%&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp B'
        right_click_commands:
       - '[close]'
        - '[player] warp B'
      B:
        material: WOOL
        data: 8
        slot: 1
        priority: 4
        display_name: '&bB &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f100'
        - '&7Status: &cLOCKED'
        left_click_commands:
       - '[close]'
        - '[player] warp B'
        right_click_commands:
       - '[close]'
        - '[player] warp B'
      C-COMPLETE:
        material: WOOL
        data: 7
        slot: 2
        priority: 1
        view_requirement:
          requirements:
            complete:
              type: string equals
              input: '%player_has_permission_ezranks.rank.D%'
              output: 'yes'
        display_name: '&cC &7- &aComplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp C'
        right_click_commands:
       - '[close]'
        - '[player] warp C'
      C-CURRENT-RANK:
        material: WOOL
        data: 13
        slot: 2
        priority: 2
        view_requirement:
          requirements:
            complete:
              type: string equals ignorecase
              input: '%ezrankspro_rank%'
              output: C
        display_name: '&cC &7- &aCurrent rank'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a100&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp C'
        right_click_commands:
       - '[close]'
        - '[player] warp C'
      C-NEXT-RANK:
        material: WOOL
        data: 8
        slot: 2
        priority: 3
        view_requirement:
          requirements:
            complete:
              type: string equals ignorecase
              input: '%ezrankspro_rank%'
              output: B
        display_name: '&cC &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &a%ezrankspro_progress%&f%'
        left_click_commands:
       - '[close]'
        - '[player] warp C'
        right_click_commands:
       - '[close]'
        - '[player] warp C'
      C:
        material: WOOL
        data: 8
        slot: 2
        priority: 4
        display_name: '&cC &7- &cIncomplete'
        lore:
        - '&7Cost: &2$&f200'
        - '&7Status: &cLOCKED'
        left_click_commands:
       - '[close]'
        - '[player] warp C'
        right_click_commands:
       - '[close]'
        - '[player] warp C'
```
