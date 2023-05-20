# Lab Report 3
## Researching Commands
I will be researching grep and looking for alternate ways I can use this command.
## **grep -r**
grep -r allows users to find a specific string in a directory and in other subdirectories.
* I used grep -r to find a broad word and see if that would work or break my computer this was the result when i used command
grep -r "and":

// The output was too large so I was only able to provide an image
![Image](andexample.png)
Here we see that it is going through all the files in the technical/ directory. It is not clear through picture but it has files from the biomed, plos, 911report and government directories.
* I also used grep -r to look for a more specific word, this is what happened when I searched for grep -r "mitochondria":
```
# [cs15lsp23pj@ieng6-203]:technical:94$ grep -r "mitochondria"
biomed/1471-2091-2-13.txt:          structure of the bovine mitochondrial F
biomed/1471-2091-2-13.txt:        endonuclease in yeast mitochondria. These authors studied
biomed/1471-2091-3-8.txt:        mitochondria (α-ketoglutarate dehydrogenase complex being
biomed/1471-2091-3-8.txt:        enzyme-bound with much of this within mitochondria [ 4 5 ]
biomed/1471-2091-3-8.txt:        Hence, thiamine transport, including that by mitochondria,
biomed/1471-2091-3-8.txt:        [ 7 8 9 10 11 12 ] . Thiamine uptake by mitochondria has
biomed/1471-2091-3-8.txt:        cytosolic and mitochondria cannot convert thiamine to ThDP
biomed/1471-2091-3-8.txt:        uptake of ThDP by rat liver mitochondria characterized by a
biomed/1471-2091-3-8.txt:        the physiological significance of the mitochondrial ThDP
biomed/1471-2091-3-8.txt:        uptake just decribed is uncertain. Within mitochondria,
biomed/1471-2091-3-8.txt:        Thiamine or ThDP entry into mitochondria from TRMA cells
biomed/1471-2091-3-8.txt:        in mitochondria are much less affected (as revealed by loss
biomed/1471-2091-3-8.txt:        uptake of thiamine and especially ThDP by mitochondria from
```
// I have provided this image to show that command searches multiple files.
![Image](mitochondriaexample.png)
Here we can see more clearly that this function searches through both biomed and plos files. 

I used the following website to get information on the command: [Link](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

---
## **grep -c**
What if I wanted to see how many times the word "and" is used in a specific file, the command grep -c counts how many lines contain the word "and"
* I will test grep -c to find how many lines "and" appears in the file pmed.0020278.txt by using the command: grep -c "and" plos/pmed.0020278.txt
```
# [cs15lsp23pj@ieng6-203]:technical:98$ grep -c "and" plos/pmed.0020278.txt
13
```
With this command I was able to see that the string "and" is found on 13 lines in this file.
* I will test grep -c to find what occurs if I look for a string that does not exist in a file by using the command: 
```
# [cs15lsp23pj@ieng6-203]:technical:99$ grep -c "toes" biomed/gb-2003-4-2-r9.txt 
0
```
We can see here that if a word does not exist in a file the command grep -c will still work and return 0.

I used the following website to get information on the command: [Link](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

---
## **grep -v**
Lets say we wanted the file to show all the lines without a specific string, we can do this with the grep -v command.
* Lets test grep -v "and" on the file plos/pmed.0020278.txt
```
# [cs15lsp23pj@ieng6-203]:technical:100$ grep -v "and" plos/pmed.0020278.txt 





        The only people who don't know in 2005 that animal research is irrelevant for human
        genetic relatives, primates have failed as research models virtually whenever they have
        been used.
        As a partial list of failures, allow me to submit the notorious forced smoking
        experiments, which allowed cigarettes to be promoted widely for decades; the abject failure
        of a quarter-century of primate research on AIDS to provide any useful insights; the false
        cardiovascular risk [1].
        The
        PLoS Medicine editors state in hopeful language that the Lassa fever
        Recall that VaxGen's AIDS vaccine (AIDSVAX) showed great success in primate studies, but
        was an abject failure in two human clinical trials, including a trial of over 2,500
        individuals [4].
        Consider the fruitless decades-long effort to produce an AIDS vaccine in primates, the
        failure to produce even a single case of human AIDS in any primate studied, or the failure
        imperatives dictate that no animal model, even higher primates, gives information
        applicable to humans. The Human Genome Project [5] tells us that there is sufficient
        PLoS Medicine is now promoting monkey research?
        I am very disappointed that
        PLoS Medicine has regressed to reporting animal research. It is
        of animal research to the historical dustbin, PLoS has chosen to re-introduce an
```
Here we can see that the file that originally had 13 lines with the string "and", is now displayed with none of these strings.

* Now I will be testing what would occur if we got more specific with what we want not to be shown using the command: grep -v "and the" plos/pmed.0020278.txt

```
# [cs15lsp23pj@ieng6-203]:technical:102$ grep -v "and the" plos/pmed.0020278.txt 


        The only people who don't know in 2005 that animal research is irrelevant for human
        disease are those who don't understand it or those who benefit from it. As a physician,
        clinical researcher, and former animal researcher, I know that though they are our closest
        genetic relatives, primates have failed as research models virtually whenever they have
        been used.
        As a partial list of failures, allow me to submit the notorious forced smoking
        experiments, which allowed cigarettes to be promoted widely for decades; the abject failure
        of a quarter-century of primate research on AIDS to provide any useful insights; the false
        leads and dangerous vaccines produced during polio research (verified by Albert Sabin,
        himself); the failure of primate studies to improve risks for birth defects and premature
        cardiovascular risk [1].
        The
        PLoS Medicine editors state in hopeful language that the Lassa fever
        vaccine was successful in four monkeys, and, thus, is a suitable agent for human study [2].
        Recall that VaxGen's AIDS vaccine (AIDSVAX) showed great success in primate studies, but
        was an abject failure in two human clinical trials, including a trial of over 2,500
        injection drug users in Thailand [3] and a multinational trial of over 5,000 high-risk
        individuals [4].
        Consider the fruitless decades-long effort to produce an AIDS vaccine in primates, the
        failure to produce even a single case of human AIDS in any primate studied, or the failure
        to identify even one useful AIDS drug from primate studies. Genetic and physiological
        imperatives dictate that no animal model, even higher primates, gives information
        applicable to humans. The Human Genome Project [5] tells us that there is sufficient
        genetic diversity among humans that pharmacogenetic and pharmacogenomic techniques will
        have an increasing role in overcoming problems related to polymorphisms and other
        variations. We can't even apply scientific findings uniformly to humans, and
        PLoS Medicine is now promoting monkey research?
        I am very disappointed that
        PLoS Medicine has regressed to reporting animal research. It is
        discouraging that in this era of rapid biomedical advancement, and appropriate relegation
        of animal research to the historical dustbin, PLoS has chosen to re-introduce an
        anachronistic, medically discredited, and unethical research tool to its reporting.

```

In this code we see that the string "and" can now be seen in the output but the line containing "and the" is now gone.

I used the following website to get information on the command: [Link](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

--- 
## **grep -w**
In the second example for the command grep -r we can see that all the lines that had the string "mitochondria" are displayed including the string "mitochondrial". How do we stop this from happening? This is where grep -w comes in handy. grep -w looks for only the specific string that we have inputed.
* I will now look for the string "mitochondria" in the file that had the string "mitochondrial using the command:grep -w "mitochondria" biomed/1471-2091-3-8.txt
 
```
[cs15lsp23pj@ieng6-203]:technical:103$ grep -w "mitochondria" biomed/1471-2091-3-8.txt 
        mitochondria (α-ketoglutarate dehydrogenase complex being
        enzyme-bound with much of this within mitochondria [ 4 5 ]
        Hence, thiamine transport, including that by mitochondria,
        [ 7 8 9 10 11 12 ] . Thiamine uptake by mitochondria has
        cytosolic and mitochondria cannot convert thiamine to ThDP
        uptake of ThDP by rat liver mitochondria characterized by a
        uptake just decribed is uncertain. Within mitochondria,
        Thiamine or ThDP entry into mitochondria from TRMA cells
        in mitochondria are much less affected (as revealed by loss
        uptake of thiamine and especially ThDP by mitochondria from
          Uptake of thiamine by cells and mitochondria
          thiamine uptake by normal lymphoblast mitochondria.
          Interestingly, mitochondria from TRMA lymphoblasts did
          as did mitochondria form normal lymphoblasts. No
          difference in uptake of thiamine by TRMA mitochondria was
          Uptake of ThDP by mitochondria
          Although mitochondria from lymphoblasts (above) and
          and mitochondria cannot convert thiamine to ThDP [ 14 16
          mitochondria, a possibility demonstrated previously with
          fashion as uptake by normal mitochondria (fig. 4). The
          affinity uptake component for mitochondria of both cell
          mitochondria isolated from normal lymphoblasts. The
          results indicate that although mitochondria from TRMA
          by mitochondria from fibroblasts and neuroblastoma cells
          mitochondria isolated from
          folate into mitochondria. For reasons discussed below,
          human mitochondria (data not shown).
        As has been reported for mitochondria of rat liver [ 13
        ] , mitochondria from human lymphoblasts were found herein
        Surprisingly, mitochondria derived from TRMA
        and the lack of such uptake by TRMA mitochondria and TRMA
        mitochondria may be carried out by the same transporter or
        significance of thiamine uptake by mitochondria is unknown
        since mitochondria cannot form ThDP from thiamine [ 14 15
        We find that mitochondria from a variety of human cell
        entry into mitochondria. Earlier work with rat liver
        mitochondria identified a ThDP uptake system with an
        transport of folates into mitochondria, and the responsible
        mitochondria, making analogies to the ability of the plasma
        with high affinity kinetics similar to that of mitochondria
        max values. Neuroblastoma mitochondria
        variation in ThDP uptake capacity by mitochondria may
        cell indicate that such enzymes in mitochondria are
        of thiamine/ThDP into mitochondria in TRMA cells even
        transport mechanism for TRMA mitochondria is consistent
          mitochondria [ 23 ] and were a kind gift from L. Chasin
          Isolation of mitochondria
          Uptake of thiamine and ThDP by mitochondria
          Uptake of thiamine and ThDP by mitochondria was
          potassium phosphate, pH 7.4) and the mitochondria were
          labeled thiamine or ThDP taken up by the mitochondria was

```

In this code we can see that only the string "mitochondria" is found in the output.
* What happens if we search for an empty string using the command grep -w, I will test this using command: grep -w "" biomed/1471-2091-3-8.txt

 ```
[cs15lsp23pj@ieng6-203]:technical:104$ grep -w "" biomed/1471-2091-3-8.txt




        Background
        Thiamine is a water-soluble, B-complex vitamin that
        cannot be synthesized by mammals, and thus thiamine can be
        obtained only from dietary intake. This can lead to severe
        consequences in humans when thiamine is limiting; thiamine
        deficiency may result in beriberi and the Wernike-Korsakoff
        syndrome [ 1 2 ] . Being positively charged and present in
        relatively low plasma concentrations, thiamine movement
        across cellular membranes requires transporters. Upon being
        taken up by a cell, thiamine is rapidly diphosphorylated by
        thiamine diphosphokinase to give thiamine diphosphate
        (ThDP) [ 3 ] . Thus, thiamine represents only a few percent
        of the total cellular thiamine/thiamine phosphate
        derivatives. ThDP serves as a cofactor for several enzymes
        that are found both in the cytosol (transketolase) and
        mitochondria (α-ketoglutarate dehydrogenase complex being
        the most studied example). The intracellular concentration
        of ThDP has been estimated at 30 μM, with only about 7
        percent being free cytosolic and the remainder being
        enzyme-bound with much of this within mitochondria [ 4 5 ]
        . Previous findings indicate a complex, cell-type dependent
        regulation of compartmentalization and intracellular pools
        of thiamine and its phosphorylated derivatives in response
        to fluctuating extracellular thiamine levels [ 4 5 6 ] .
        Hence, thiamine transport, including that by mitochondria,
        is of interest.
        Thiamine entry into mammalian cells occurs by a
        saturable, high affinity transporter that is deficient in
        humans with thiamine-responsive megaloblastic anemia (TRMA)
        [ 7 8 9 10 11 12 ] . Thiamine uptake by mitochondria has
        been demonstrated [ 13 ] , yet thiamine diphosphokinase is
        cytosolic and mitochondria cannot convert thiamine to ThDP
        [ 14 15 16 ] . Barile and coworkers demonstrated saturable
        uptake of ThDP by rat liver mitochondria characterized by a
        K
        m of around 20 μM. Although the
        estimated concentration, in mice and human cells, of
        intracellular ThDP is about 30 μM, much of this is found in
        a low turnover pool representing enzyme-bound ThDP [ 4 17 ]
        . The estimated concentration of free cytosolic ThDP
        available for intracellular transport is about 10% of the
        total concentration and thus 2 to 3 μM [ 4 17 18 ] . Hence
        the physiological significance of the mitochondrial ThDP
        uptake just decribed is uncertain. Within mitochondria,
        ThDP can be converted to thiamine monophosphate [ 19 ] .
        Thiamine or ThDP entry into mitochondria from TRMA cells
        has not been studied. Interestingly, ThDP-utilizing enzymes
        in mitochondria are much less affected (as revealed by loss
        of activity) upon progressive depletion of thiamine
        available to TRMA cells than are ThDP-utilizing enzymes of
        the cytosol [ 6 ] . For these reasons, we have examined the
        uptake of thiamine and especially ThDP by mitochondria from
        several human cell types, including cells from TRMA
        patients.
        
        ...

```

(Code was trimmed for formatting purposes, but the entirety of biomed/1471-2091-3-8.txt was being outputted)
This command shows all the lines in the file, so from this we can see that using this command with an empty line will return all lines.

I used the following website to get information on the command: [Link](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)
