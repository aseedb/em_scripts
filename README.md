# em_scripts
small scripts for electron microscopy image processing

### images_to_stack.ipyn
This jupyter notebook converts a series of individual mrc files, i.e. a tilt series, to an mrc stack of desired name. In addition it creates an .ang file containing the tilt angles of the images. In the stack, the images are sorted according to their tilt angle, from the lowest to the highest tilt angle. The script searches for mrc files with the file name pattern input by the user, in the current directory. Tilt angle must be included in the file name between brackets ("my_file[10.50]pattern.mrc"). This corresponds to file names output by FEI tomo software. 
#### requirements
- python3
- [mrcfile](https://anaconda.org/conda-forge/mrcfile)
- numpy
## Additional stuff
### convert a series of tif stacks to mrc stacks (and transfer the tif pixel size to mrc pixel size)
we use fishshell for that
output mrc stacks will be saved in the current directory
```
for file in tif_stack_dir/*.tif
    set outname (basename $file .tif).mrc
    tif2mrc -P $file $outname
end
```
