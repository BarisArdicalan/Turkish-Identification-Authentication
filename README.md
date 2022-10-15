# Turkish-Identification-Authentication
Turkish Identification Authentication For Python

tc="30349865626"
harf=False
try:
    tc_liste = list(map(int,tc))
except:
    harf=True
if harf==False:
    adet=0
    for i in tc_liste:
        adet +=1
    if adet ==11:
        if tc_liste[0]!=0:
            birinci_islem = (sum(tc_liste[0:9:2])*7)-(sum(tc_liste[1:9:2]))
            bizim_buldugumuz=tc_liste[0:9]
            bizim_buldugumuz.append(birinci_islem%10)
            bizim_buldugumuz.append(sum(bizim_buldugumuz)%10)
            bizim_buldugumuz_tc=""
            for i in bizim_buldugumuz:
                bizim_buldugumuz_tc +=str(i)
            if bizim_buldugumuz_tc == tc:
                print("TC Kimlik Doğru")
            else:
                print("TC Kimlik Yanlış")
        else:
            print("TC Kimlik Yanlış")
    else:
        print("TC Kimlik Yanlış")
else:
    print("TC Kimlik Yanlış")

