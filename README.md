# Kod-do-wojny
Kod do wojny z zajęć PZPM


clear
clc
close all


%generacja 4 kolorow
czerwo=[1:13];
dzwonek=[1:13];
zoladz=[1:13];
wino=[1:13];


%skladanie talii
talia(1,13)=zeros;
talia(1,1:13)=czerwo;
talia(1,14:26)=dzwonek;
talia(1,27:39)=zoladz;
talia(1,40:52)=wino;

%sortowanie talii, niepotrzebne
sort(talia);


%tasowanie
[m,n] = size(talia);
idx = randperm(n);
talia2=talia;
talia2(1,idx)=talia(1,:);


%rozdawanie kart
talia_gracz1=talia2(1:26);
talia_gracz2=talia2(27:52);



%gra
[a,b]=size(talia_gracz1);
[c,d]=size(talia_gracz2);


while size(talia_gracz1)~=0 | size(talia_gracz2)~=0
    
    
stol=[talia_gracz1(1:1) talia_gracz2(1:1)]


    
if stol(1,1)>stol(1,2)
    disp('Gracz 1 wygral')
    talia_gracz1(:,1)=[];
    talia_gracz2(:,1)=[];
    talia_gracz1(1,b:b+1)=stol;
elseif stol(1,1)<stol(1,2)
    disp('Gracz 2 wygral')
    talia_gracz1(:,1)=[];
    talia_gracz2(:,1)=[];
    talia_gracz2(1,d:d+1)=stol;
else stol(1,1)==stol(1,2)
    talia_gracz1(:,1)=[];
    talia_gracz2(:,1)=[];
    %dopisac warunek remisu
    disp('ble ble')
end

disp('Wcisniej spacje by przejsc do kolejnego rozdania') 
pause

end




%repmat randperm
