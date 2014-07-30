Large Scale PSG Analysis Student Projects
=========================================
Making the analysis of thousands of sleep studies common place is the motivation for the projects described below. The projects are targeted at interdisciplinary types, engineers and computer scientists. All of the projects require programming. The projects could be developed in many different programming languages. 

Are you a biology major and want to strengthen your programming skills, well there will be projects for you too. I suggest you start with a tutorial for your language of choice.  Python and JAVA are the most popular languages. MATLAB is my language of choice. There may be a slight bias for the selection of examples that include MATLAB source code.

Do you have a project you want to post? Send me and email and I will post it here. 

Did you complete one of the projects? Email me so that we can post a link to your solution.


#### Data Access Projects

1. **Porting low level signal file loaders**. I have developed a set of loaders for sleep file written in European Data format. It would be nice to have the MATLAB versions ported to Python, JAVA and Octave.  The two loaders are [BlockEdfLoad](https://github.com/DennisDean/BlockEdfLoad/blob/master/README.md) and [BlockEdfLoadClass](https://github.com/DennisDean/BlockEdfLoadClass/blob/master/README.md). Porting the loaders would provide and oportuniting to think about efficient loading of large data sets. My loaders are relatively effienct and use many modern MATLAB features. You will have to work through the MATLB syntax and find parallels in a second language. What fun!  Beyond the fun to be had, having similar tools across most commonly used languages is a way to promote reproducible research.

2. **More Efficent Load**. The loaders mentioned above, load all the data and only pass back the data (signals and sleep epochs) specified by the load command. I suspect that refining the loader to only load what is needed would result in an efficent way could reduce load times in practice. Look at the signal load area within [BlockEdfLoad](https://github.com/DennisDean/BlockEdfLoad/blob/master/README.md) or [BlockEdfLoadClass](https://github.com/DennisDean/BlockEdfLoadClass/blob/master/README.md). The task is to infer the most efficent data loading strategy based on the user request. Most sleep files have between ten and twenty signals.  However, most analyses would require only a single signal.

3. **Low Level XML parser**.  Sleep annotation files used for the [National Sleep Research Resource](https://sleepdata.org/) are written in [XML](http://en.wikipedia.org/wiki/XML) format. We are currently reading the XML file with a MATLAB provided JAVA interface.  A low level parser that allows the schema to be inferred would allow us to load and check according to a schema.  There are several types of sleep annotation files written in XML.  A generic loader with a test schema schema as input could be configured to load/check different XML file types/version.  An example of our XML loader and file examples can be found [here](https://github.com/DennisDean/LoadCompumedicsAnnotationsClass). This project is suited for a person who has taken or wants to take a [compiler](http://en.wikipedia.org/wiki/Compiler) design course.  The project motivation is to be able to load/process files written over 20 years that have known issues.  A smarted loader would allow for more robust tools to be developed.

#### Signal Generation and Analysis

4. **Sleep EEG Spectral Simulations**. There are characteristic spectra during [NREM](http://en.wikipedia.org/wiki/Non-rapid_eye_movement_sleep) and [REM](http://en.wikipedia.org/wiki/Rapid_eye_movement_sleep) sleep. Moreover, these spectra change during the life course.  As we developed automated analysis tools, it would be nice to have the ability to generated simulated EEG signals for which to perform simulation studies. A spectral editor that would allow a domain expert to interactively edit/save/simulate chaaracteristic spectra would be a total bonus.  There spectra could then be used to simulate NREM-REM patterns over the night. 

Potential Starting Point: I found a nice project that allows you to edit data in the [time domain](http://www.mathworks.com/matlabcentral/fileexchange/23526-waveform-generator-gui) and automatically produces spectra.  The project would have to inverted so that editing was done in the frequency domain and simulations were done in the time domain. This project would require some learning to be done about sleep and sleep stages inorder for the tool to be accepted by domain experts. This project goes beyond the cursory fft of a square wave done in many quantiative classes. Just to add a little fun, it would be nice for the generating function to create sleep files (EDF format), to use sleep annotation files to generate random instances and to upload spectral results so that simulations of individuals could be formed. The project as described would require traversing low level read/write, signal processing functionality and GUI devleopment. Nice way to strengthed and add new skills.  

5. **GUI interface for Source Localization Model**. Generating simulated EEG data from a [source localization model](http://en.wikipedia.org/wiki/Magnetoencephalography#Source_localization) could be a nice way to connect brain physiology and EEG sleep recordings. Alas, I have not found publicallly available source code to start from.  There is some nice source code for [simulating EEG data](http://www.cs.bris.ac.uk/~rafal/phasereset/) from an evoked response source model. Adding a GUI with the ability to select parameters and to output simulated data to an EDF file would be a nice project. Initially, a student would begin to understand how source models can be used to generate data.  I am convinced it only a matter of time before source localization models for sleep applications are readily avilable. It should be straight forward to make the implementation flexible enough to load multiple source models.


6. **Large Scale Spectral and Coherence Analysis**. I wrote an effient spectral analysis and coherence program.  But I can't sleep at night because I am not using all the cores on my 6 core machine.  I am sure there are ways to improve the running time, especially the coherence analysis. The datasets we work with are in the order of hundreds of Gigabytes. The uploaded [spectral analysis program](https://github.com/DennisDean/SpectralTrainFig/blob/master/README.md) includes examples. Are there strategies for processing the data on desktop that enable more efficent processing? Can the most efficent loading/analysis algorithms be inferred from the analysis specification? 

Why do this? Increasinlyg efficent software is often the analysis bottleneck. My personal game plan is to move towards analyzing tens of thousands of sleep files by making better use of multi-core machine. I expect that computers with 12-24 cores (similar to early computer clusters) will be readily availabe/inexpepensive in 5 years. Just planning to have the software in place.

#### Signal Specific Problem
The current EDF software tool set I have developed ([Data Access and Visualization for Sleep](https://github.com/DennisDean/DAVS-Toolbox/blob/master/README.md)) makes access of data in an EDF file pretty straight forward. I see the next steps to include developing signal specific add-ons/extensions to the EDF loader. [Physionet](http://www.physionet.org/) had a bunch of signal processing tools that can be used to do a wide range of analyes from the most common platforms (PC, Macintosh, Unix). 

7. **Adapt the EEG Spectral Analysis Program to Perform ECG HRV analysis**. 

#### Traditional Sleep Analysis Tools.

8. **Add Sleep staging functionality to the [EDF Viewer](https://sleepdata.org/tools/edf-viewer)**.

#### Cognitive Assessment

6. **Two Dimensional MAZE test**.  One of the [most interesting studies](http://onlinelibrary.wiley.com/doi/10.1111/j.1365-2869.2005.00484.x/full) I have read involved giving maze test to people who are sleep deprived.  The study was done with paper mazes. Why not do the same thing on a PC or tablet. It stuck me as rediculously fun to write software to interactively generate and test maze performance. Beyond the fun to be had, generating random mazes with the same properties would be fun. I found sites with information on how to generate [random mazes](http://www.mathworks.com/matlabcentral/fileexchange/6705-maze) and there are tools for [generating cognitive tests](https://psychtoolbox.org/HomePage). The two would just have to be put together.  This is the type of projectd that could be paired up with people across disciplines.  Most researachers won't use a tool with out validation.  Generate some study results for extra credits. Writing a MAZE program was one of my first projects.  You would learn about data stuctures, algrithmns and random generation. Developing a cognitive test would required you to think about system response time and recording of ingormation.
