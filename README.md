# level.dat History

- [inf-20100327](https://github.com/Team-Lodestone/LevelDatHistory/commit/39ea236feadb1a553f9866fd2f709e4ab8ee4d35)
  - Introduced level.dat
- [inf-20100413-1953](https://github.com/Team-Lodestone/LevelDatHistory/commit/474de3c12a252b660c99c227278df54882539489)
  - Removed `id` tag under the `Player` compound tag  
  - Reordered some keys
- [inf-20100625-1917](https://github.com/Team-Lodestone/LevelDatHistory/commit/0092e2ef92c344052ce178bacd2104ac01040520)
  - Added boolean byte tag `onGround` under `Player`
    - Used to tell if the player is on a block 
  - Reordered some keys
- [a1.0.4](https://github.com/Team-Lodestone/LevelDatHistory/commit/2b78c41b588f498f86a582b4232c2dfc947a34bc)
  - Added boolean byte tag `SnowCovered`
    - Used to determine if new chunks should be covered in snow or not
  - Normalized the values inside the `Motion` tag (unverified)
    - ```diff
      - Motion: [0d, -0.08d, 0d]
      + Motion: [0d, -0.0784000015258789d, 0d]
      ```
- [a1.2.0](https://github.com/Team-Lodestone/LevelDatHistory/commit/8472b8a6b5334878207548e4ee46923804978aad)
  - Added int tag `Dimension` under `Player`
    - Stores the dimension (by id) the player was in when saved
- [b1.3-1713](https://github.com/Team-Lodestone/LevelDatHistory/commit/6a379eaa46800f755f3e1b0cddb062947c5c30c0)
  - Added boolean byte tag `Sleeping` under `Player`
    - Used to determine if the player should be sleeping on join
  - Added short tag `SleepTimer` under `Player`
    - Stores the amount of ticks the player has been sleeping for
  - Added string tag `LevelName`
    - Stores the name of the world
  - Added int tag `version`
    - Stores the version of Minecraft the world was last loaded in
    - The value of this tag was never changed from `19132` until `version` was replaced by `DataVersion`
- [b1.5](https://github.com/Team-Lodestone/LevelDatHistory/commit/28455ffb25a0a171d22ff9b5ad04f1b3f2f47796)
  - Added int tag `rainTime`
    - Stores the amount of ticks until it will rain in the world.
    - Once this hits 0, `raining` will be set to `true/1` and this value will be assigned a new random number.
  - Added int tag `thunderTime`
    - Stores the amount of ticks until a thunderstorm will start in the world.
    - Once this hits 0, `thundering` will be set to `true/1` and this value will be assigned a new random number.
  - Added boolean byte tag `raining`
    - Determines whether it was raining when the world was saved
  - Added boolean byte tag `thundering`
    - Determines whether there was a thunderstorm when the world was saved
  - Moved `LastPlayed` tag from top of `Data` to below `version`
  - Moved `LevelName` tag below `LastPlayed`
- [b1.6-test_build_3](https://github.com/Team-Lodestone/LevelDatHistory/commit/cd57b792416b7ad2a58355b0d0be99a0e6416659)
  - `Pos`' Y tag now stores `pos.y + 2` to prevent the player from spawning into the world inside a block (unverified)
    - ```diff
      - Pos: [0d, 94.6200000047684d, 0d]
      + Pos: [0d, 96.2400000095367d, 0d]
      ```
- [b1.6.5](https://github.com/Team-Lodestone/LevelDatHistory/commit/060dc11265bc48b2ddaf5257ba01ea951e3dc4b7)
  - Reverted `Pos`' Y tag fix
    - ```diff
      - Pos: [0d, 96.2400000095367d, 0d]
      + Pos: [0d, 94.6200000047684d, 0d]
      ```
- [b1.8-pre1-081459](https://github.com/Team-Lodestone/LevelDatHistory/commit/944372ae2df71008784758ad192036bd747c3c38)
  <!-- TODO add descriptions -->
  - Added float tag `foodSaturationLevel` under `Player`
    - Default value is `5f`
  - Added int tag `XpLevel` under `Player`
    - Default value is `0`
  - Added int tag `Xp` under `Player`
    - Default value is `0`
  - Added int tag `XpTotal` under `Player`
    - Default value is `0`
  - Added int tag `foodLevel` under `Player`
    - Default value is `20`
  - Added float tag `foodExhaustionLevel` under `Player`
    - Default value is `0f`
  - Added int tag `foodTickTimer` under `Player`
    - Default value is `0`
  - Added int tag `GameType`
    - Determines the Gamemode (by id) that players will use
    - Default value is `0`
    - ```cpp
      {
        {0, "survival"}, // survival mode
        {1, "creative"}  // creative mode
      }
      ```
   - Added boolean byte tag `MapFeatures`
     - Default value is `true/1` on a new world, otherwise `false/0` for upgraded worlds (unverified)
     - Determines whether to generate features such as strongholds and villages
- [b1.9-pre2](https://github.com/Team-Lodestone/LevelDatHistory/commit/f24361568b4194c5f5cb620eb212bc9bf2814d37)
  - Added boolean byte tag `hardcore`
    - Determines whether players are in "hardcore" mode, which prevents the player from playing the world after they have died.
- [b1.9-pre4-1415](https://github.com/Team-Lodestone/LevelDatHistory/commit/0ea32571e1cd97512e3a94bc1dbe0e5b1ce9d40a)
  - Removed int tag `Xp` in favor of new float tag `XpP`
    - Default value of `XpP` is `0f`
- [b1.9-pre5](https://github.com/Team-Lodestone/LevelDatHistory/commit/ae68ae430b99d80dfc92c3dce286db08b2d9464d)
  - Added compound tag `abilities` under `Player`
    - This tag contains 4 new tags:
      - boolean byte tag `invulnerable`
      - boolean byte tag `mayfly`
      - boolean byte tag `instabuild`
      - boolean byte tag `flying`
 
