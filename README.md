I am frustrated by the absense of driver of sabre hifi on linux. I searched for many sites but there is no answer. I decided to create a project to work with that. I don't have enough knowledge about that so if you are interested in this project, please star it. After we get enough people, we can discuss and make progress.

I made some progress on this but it may not work for others. ~~What I did is flash a unlcoked bios (chipset menu in bios unlocked), then adjust `DSP` to be enabled in PCHIO/HDAudio configuration.~~(This may not be mandatory from my experiment results) In addition, the patch is required as well. The critical part is to put 0x1b(VREF) pin to something over HIZ, it triggered both `AARELAY` and `AAOP1622_EN`. I used hda_analyzer python script to do the job(uploaded required script, use with `sudo`). Then I used `pavucontrol` to set the output to be SPDIF since the board use SPDIF to transfer audio between alc898 codec and es9018 DAC. After that, It should output some music.

~~It might be possible to do the job without flashing bios because the DAC is controlled by I2C. However, on my model, the I2C bus is on the second EC, which is not exposed to the OS. If we can find a way to control the I2C bus, it is possible to use the DAC without an unlocked bios. The I2C communications I captured are located in `captures` folder. Have fun.~~
