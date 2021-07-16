# Connectome Generation
_by Lawrence Binding_

```{admonition} Estimated Time 
:class: TIP
20 minutes
```

Now we have our whole phantom tractogram! Now lets learn how to generate our very own connectome. 



<style>
h1 {text-align: center;}
h2 {text-align: center;}
</style>

--- 

## Atlas 
To generate our connectome, we need to have an atlas. A cortical atlas typically contain the cortex split up into functional or anatomical regions. Each region has a unique number assigned to it. There are hundreds of different types of atlas out there, the decision on which one to use will largely depend on what you intend to measure. Thankfully, we don't have that much decision when it comes to the fibrecup phantom. Located in the connectome/ folder is a file called "fibre_parc.nii.gz". Open it in overlay, and disable interpolation (located in: tools > overlay, bottom of the pannel). Hover over each region and at the bottom left it tells you the number of each region its assigned to. The "fibre_parc.txt" is a text file which tells you where each region is located. Every atlas should come with one of these.

```shell
mrview fibrecup_denoise_gibbs_preproc_biaCorr.mif -load.overlay connectome/fibre_parc.nii.gz 
```


<figure>
<img src="../../_static/img/atlas.png" alt="colab" style="width:464px;height:371px;">
<figcaption>Fig.1 - mrview showing the fibre parcellation file.</figcaption>
</figure>


## Connectome Generation 
So lets move onto generating our connectome. We can do so using the tck2connectome command: 

```shell
tck2connectome -symmetric -zero_diagonal tcks_10k.tck fibre_parc.nii.gz connectome.csv 
```
* -symmetric is asking it to return a symmetrical matrix 
* -zero_diagonal is asking it to not return connection-to-connection results. 

## Connectome inspection
Open up the CSV sheet in Excel, 


<style>
  .iframe-container {
		text-align:center;
  		width:100%;
  }
</style>


```{admonition} Further reading
- blah blah 
- blah blah
- blah blah
- blah blah

```
