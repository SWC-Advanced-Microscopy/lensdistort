# lensdistort
Correct image barrel or pincushion distortion, or apply these to non-distorted images. 
This function is a modified version of that written by Jaap de Vries [on the File Exchange](https://ch.mathworks.com/matlabcentral/fileexchange/37980-barrel-and-pincushion-lens-distortion-correction). 
The present code has been modified in the following ways:

* Default interpolation is set to `linear`.
* The padding value defaults to image minimum and can be modified via an input argument.
* It's possible to set a different value of `k` for rows and columns (see example below).
* An image stack can be supplied and this is processesed more efficiently by feeding the whole stack as an input to `tformarray`. 
* Affine transformation along with distortion correction.


```
c=checkerboard(25,30);
inputIm = c(:,:,1)*2^8;
 
figure
subplot(2,2,1), imagesc(inputIm), title('orig')
subplot(2,2,2), imagesc(lensdistort(inputIm, 0.2)), title('barrel')
subplot(2,2,3), imagesc(lensdistort(inputIm, -0.2)), title('pincushion')
subplot(2,2,4), imagesc(lensdistort(inputIm,[-0.2,0.4])), title('both') 
```
<img src="https://github.com/raacampbell/lensdistort/blob/master/docs/example_checker.png" />
