# arcgridwrite
Write gridded data set in Arc ASCII Grid Format

    arcgridwrite(fileName,X,Y,Z)- converts data in a matlab
    grid into a text file in Arc ASCII Grid Format. 
 
    INPUTS
        fileName:  output filename including extension
        X:         X coordinates (vector 1 x N) 
        Y:         Y coordinates (vector m x 1) 
        Z:         gridded data (m x n) 
 
    SYNTAX AND OPTIONS
        arcgridwrite('D:\tools\bathyGrid.asc',X,Y,Z)
 
        arcgridwrite(...,'precision',5) - changes default output
            from 3 to 5 decimal places.
 
        arcgridwrite(...,'nodata',-32768) - changes no data value
            from -9999 (default) to -32768.
 
        arcgridwrite(...,'grid_mapping','center') - changes the 
            grid spatial reference from 'corner' (default) to 'center'.
            This is useful when combining output from the mapping
            toolbox's PIXCENTERS function.               
 
    EXAMPLE 1 - create a raster grid of the peaks function
        [X,Y,Z]=peaks(100);
        arcgridwrite('peaksArc.asc',X(1,:),Y(:,1),Z,'precision',5)
 
    NOTES 
    Because the Arc ASCII format has only one parameter for cell size,
    both X and Y must have the same, non-varying grid spacing.  
