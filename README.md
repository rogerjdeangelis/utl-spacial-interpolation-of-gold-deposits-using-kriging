# utl-spacial-interpolation-of-gold-deposits-using-kriging
Where are the best locations to find gold use kriging
    Where are the best locations to find gold use kriging                                                                        
                                                                                                                                 
    Kriged output                                                                                                                
    https://tinyurl.com/y7srxnay                                                                                                 
    https://github.com/rogerjdeangelis/utl-spacial-interpolation-of-gold-deposits-using-kriging/blob/master/gold.png             
                                                                                                                                 
    github                                                                                                                       
    https://tinyurl.com/yamjkplb                                                                                                 
    https://github.com/rogerjdeangelis/utl-spacial-interpolation-of-gold-deposits-using-kriging                                  
                                                                                                                                 
    sas Forum                                                                                                                    
    https://tinyurl.com/yardprwq                                                                                                 
    https://communities.sas.com/t5/SAS-Programming/Bilinear-interpolation-in-SAS/m-p/640174/highlight/true#M190603               
                                                                                                                                 
    This solution                                                                                                                
    https://rspatial.org/terra/pkg/9-predict.html#kriging                                                                        
                                                                                                                                 
    *_                   _                                                                                                       
    (_)_ __  _ __  _   _| |_                                                                                                     
    | | '_ \| '_ \| | | | __|                                                                                                    
    | | | | | |_) | |_| | |_                                                                                                     
    |_|_| |_| .__/ \__,_|\__|                                                                                                    
            |_|                                                                                                                  
    ;                                                                                                                            
                                                                                                                                 
    options validvarname=v7;  ** importamt;                                                                                      
    libname sd1 "d:/sd1";                                                                                                        
    data sd1.have;                                                                                                               
     input x y gold @@;                                                                                                          
    cards4;                                                                                                                      
    181072 333611 1022 181025 333558 1141 181165 333537 640 181298 333484                                                        
    257 181307 333330 269 181390 333260 281 181165 333370 346 181027 333363                                                      
    406 181060 333231 347 181232 333168 183 181191 333115 189 181032 333031                                                      
    251 180874 333339 1096 180969 333252 504 181011 333161 326 180830 333246                                                     
    1032 180763 333104 606 180694 332972 711 180625 332847 735 180555 332707                                                     
    1052 180642 332708 673 180704 332717 402 180704 332664 343 181153 332925                                                     
    218 181147 332823 200 181167 332778 194 181008 332777 207 180973 332687                                                      
    180 180916 332753 240 181352 332946 180 181133 332570 208 180878 332489                                                      
    198 180829 332450 250 180954 332399 192 180956 332318 213 180710 332330                                                      
    321 180632 332445 569 180530 332538 833 180478 332578 906 180383 332476                                                      
    1454 180494 332330 298 180561 332193 167 180451 332175 176 180410 332031                                                     
    258 180355 332299 746 180292 332157 746 180283 332014 464 180282 331861                                                      
    365 180270 331707 282 180199 331591 375 180135 331552 222 180237 332351                                                      
    812 180103 332297 1548 179973 332255 1839 179826 332217 1528 179687                                                          
    332161 933 179792 332035 432 179902 332113 550 180100 332213 1571 179604                                                     
    332059 1190 179526 331936 907 179495 331770 761 179489 331633 659 179414                                                     
    331494 643 179334 331366 801 179255 331264 784 179470 331125 1060 179692                                                     
    330933 119 179852 330801 778 179140 330955 703 179128 330867 676 179065                                                      
    330864 793 179007 330727 685 179110 330758 593 179032 330645 549 179095                                                      
    330636 680 179058 330510 539 178810 330666 560 178912 330779 1136 178981                                                     
    330924 1383 179076 331005 1161 180151 330353 1672 179211 331175 765                                                          
    181118 333214 279 179474 331304 241 179559 331423 317 179022 330873 545                                                      
    178953 330742 505 178875 330516 420 178803 330349 332 179029 330394 400                                                      
    178605 330406 553 178701 330557 577 179547 330245 155 179301 330179 224                                                      
    179405 330567 180 179462 330766 226 179293 330797 186 179180 330710 198                                                      
    179206 330398 187 179618 330458 199 179782 330540 157 179980 330773 203                                                      
    180067 331185 143 180162 331387 136 180451 331473 117 180328 331158 113                                                      
    180276 330963 130 180114 330803 192 179881 330912 240 179774 330921 221                                                      
    179657 331150 140 179731 331245 128 179717 331441 166 179446 331422 191                                                      
    179524 331565 232 179644 331730 203 180321 330366 722 180162 331837 210                                                      
    180029 331720 198 179797 331919 139 179642 331955 253 179849 332142 703                                                      
    180265 332297 832 180107 332101 262 180462 331947 142 180478 331822 119                                                      
    180347 331700 152 180862 333116 415 180700 332882 474 180201 331160 126                                                      
    180173 331923 210 180923 332874 220 180467 331694 133 179917 331325 141                                                      
    179822 331242 158 179991 331069 129 179120 330578 206 179034 330561 451                                                      
    179085 330433 296 179236 330046 189 179456 330072 154 179550 329940 169                                                      
    179445 329807 403 179337 329870 471 179245 329714 612 179024 329733 601                                                      
    178786 329822 783 179135 329890 258 179030 330082 214 179184 330182 166                                                      
    179085 330292 496 178875 330311 342 179466 330381 162 180627 330190 375                                                      
    ;;;;                                                                                                                         
    run;quit;                                                                                                                    
                                                                                                                                 
    options ls=64 ps=44 FORMCHAR='|----|+|---+=|-/\<>*';;                                                                        
    proc plot data=sd1.have;                                                                                                     
    plot y*x=gold / contour=10;                                                                                                  
    run;quit;                                                                                                                    
                                                                                                                                 
                          Contour plot of Y*X.                                                                                   
                                                                                                                                 
         |  Symbol     gold                                                                                                      
         |                                                                                                                       
       Y |   .....     0- 200                                                                                                    
    5000 +   '''''   200- 400                                                                                                    
         |   -----   400- 600                                                                                                    
         |   =====   600- 800                       OO=                                                                          
         |   +++++   800-1000                     O - ' '                                                                        
         |   OOOOO  1000-1200                    =O -''. '                                                                       
    4000 +   XXXXX  1200-1400                   =   ' '  .                                                                       
         |   WWWWW  1400-1600                 O=-  '' '                                                                          
         |   *****  1600-1800                +  '   . '                                                                          
         |   #####  1800-2000            + W ' -' ..                                                                             
         |                        + W-#W  ==. .                                                                                  
    3000 +                     +O' -    ' - '                                                                                    
         |                     = '    . ' '. .                                                                                   
         |                     =        ''   .                                                                                   
         |                   +='' .  .  .   .                                                                                    
         |                 ==  O .. .  . . .                                                                                     
    2000 +              XO=       .'' .   .                                                                                      
         |             O===.. '     = ' .                                                                                        
         |          --- -='   .    .                                                                                             
         |        -  '' -' .   . .      * =                                                                                      
         |               - .'   .              '                                                                                 
    1000 +              '  .  . .                                                                                                
         |           =  = '= --                                                                                                  
         |                                                                                                                       
         |                                                                                                                       
         |                                                                                                                       
       0 +                                                                                                                       
         |                                                                                                                       
         -+-------------+-------------+-------------+-------------+-                                                             
          0           1000          2000          3000          4000                                                             
                                                                                                                                 
                                                                                                                                 
    *            _               _                                                                                               
      ___  _   _| |_ _ __  _   _| |_                                                                                             
     / _ \| | | | __| '_ \| | | | __|                                                                                            
    | (_) | |_| | |_| |_) | |_| | |_                                                                                             
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                            
                    |_|                                                                                                          
    ;                                                                                                                            
                                                                                                                                 
    https://tinyurl.com/y7srxnay                                                                                                 
                                                                                                                                 
    *                                                                                                                            
     _ __  _ __ ___   ___ ___  ___ ___                                                                                           
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|                                                                                          
    | |_) | | | (_) | (_|  __/\__ \__ \                                                                                          
    | .__/|_|  \___/ \___\___||___/___/                                                                                          
    |_|                                                                                                                          
    ;                                                                                                                            
                                                                                                                                 
    options ls=171 ps=200;                                                                                                       
    %utlfkil("d:/pdf/gold.pdf");                                                                                                 
    %utl_submit_r64('                                                                                                            
    library(sp);                                                                                                                 
    library(gstat);                                                                                                              
    library(haven);                                                                                                              
    library(terra);                                                                                                              
    library(SASxport);                                                                                                           
    meuse<-as.data.frame(read_sas("d:/sd1/have.sas7bdat"));                                                                      
    r <-rast(system.file("exdata/test.tif", package="terra"));                                                                   
    mg <- gstat(id = "gold", formula = gold~1, locations = ~x+y, data=meuse,                                                     
                nmax=7, set=list(idp = .5));                                                                                     
    f <- function(model, data, ...) predict(model, data, ...)[,3,drop=FALSE];                                                    
    z <- interpolate(r, mg, fun=f, debug.level=0);                                                                               
    coordinates(meuse) <- ~x+y;                                                                                                  
    crs(meuse) <- crs(r);                                                                                                        
    v <- variogram(log(gold)~1, meuse);                                                                                          
    m <- fit.variogram(v, vgm(1, "Sph", 300, 1));                                                                                
    gOK <- gstat(NULL, "log.gold", log(gold)~1, meuse, model=m);                                                                 
    fg <- function(model, d, crs, ...) {                                                                                         
        sp <- SpatialPointsDataFrame(d[,1:2,drop=FALSE], data.frame(d), proj4string=CRS(crs));                                   
        data.frame(predict(model, sp, ...))[,3:4];                                                                               
    };                                                                                                                           
    OK1 <- interpolate(r, gOK, fun=fg, debug.level=0, crs=crs(r), na.rm=FALSE);                                                  
    str(OK1);                                                                                                                    
    plot(c(OK1[[1]]));                                                                                                           
    ');                                                                                                                          
                                                                                                                                 
