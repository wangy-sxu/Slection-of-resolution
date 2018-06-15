# Slection-of-resolution

#LBP
This is a M file for the implementation of LBP feature extracation. 
LBP returns the local binary pattern image or LBP histogram of an image.
%  J = LBP(I,R,N,MAPPING,MODE) returns either a local binary pattern
%  coded image or the local binary pattern histogram of an intensity
%  image I. The LBP codes are computed using N sampling points on a 
%  circle of radius R and using mapping table defined by MAPPING. 
%  See the getmapping function for different mappings and use 0 for
%  no mapping. Possible values for MODE are
%       'h' or 'hist'  to get a histogram of LBP codes
%       'nh'           to get a normalized histogram
%  Otherwise an LBP code image is returned.
%
%  J = LBP(I) returns the original (basic) LBP histogram of image I
%
%  J = LBP(I,SP,MAPPING,MODE) computes the LBP codes using n sampling
%  points defined in (n * 2) matrix SP. The sampling points should be
%  defined around the origin (coordinates (0,0)).
%
%  Examples
%  --------
%       I=imread('rice.png');
%       mapping=getmapping(8,'u2'); 
%       H1=LBP(I,1,8,mapping,'h'); %LBP histogram in (8,1) neighborhood
%                                  %using uniform patterns
%       subplot(2,1,1),stem(H1);
%
%       H2=LBP(I);
%       subplot(2,1,2),stem(H2);
%
%       SP=[-1 -1; -1 0; -1 1; 0 -1; -0 1; 1 -1; 1 0; 1 1];
%       I2=LBP(I,SP,0,'i'); 
#getmapping
%GETMAPPING returns a structure containing a mapping table for LBP codes.
%  MAPPING = GETMAPPING(SAMPLES,MAPPINGTYPE) returns a
%  structure containing a mapping table for
%  LBP codes in a neighbourhood of SAMPLES sampling
%  points. Possible values for MAPPINGTYPE are
%       'u2'   for uniform LBP
%       'ri'   for rotation-invariant LBP
%       'riu2' for uniform rotation-invariant LBP.
%
%  Example:
%       I=imread('rice.tif');
%       MAPPING=getmapping(16,'riu2');
%       LBPHIST=lbp(I,2,16,MAPPING,'hist');
%  Now LBPHIST contains a rotation-invariant uniform LBP
%  histogram in a (16,2) neighbourhood.
%
#subscript
%Devide indexes for every class lable. 
#random arrangement
%Sample from the devided indeses in subscript
%These two function are used to guarantees the 
%class balance for each group in cross validation.
#group
%Devide the data into f equal-sized groups for cross validation
#main
%This is the main function for the resolution selection.It returns the 
%change of KL divergenge as the changes of lamada, the optimal lamada 
%and the classication accuracy.
%For example,
%set
%ngroup=5
%lamada=seq(0,2,0.005)
%accu=matrix(NA,10,length(lamada))
%count<-0
%for (j in 1:1000)
%{
%print(paste("the",count))
%     print(date())
%svm_result<-Strcrossval_ngroup_svm(x1,x2,x3,x4,x5,x6,x7,y,ngroup)
%accu[j,]=colMeans(svm_result$Acc_svm)
%count<-count+1
%}
%ave_101=colMeans(accu)
%plot(lamada,ave_101,type="b")

