This demo shows you how to merge the source and output blocks in markdown output. Note **knitr** puts R source and output in separate blocks by default.



```r
# first ``` are the end of previous source block; second ``` are the
# beginning of next output block
knit_hooks$set(chunk = function(x, options) {
    gsub("```\n+```", "", x)
})
```




See if it works:



```r
a = 1
a

## [1] 1
```




Source and output lived together happily ever in **knitr**.
