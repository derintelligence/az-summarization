# az-summarization
Azərbaycan dili üçün Abstrakt Özətləmə modeli.Dataset məsələnin həlli üçünü toplanmış təxminən 400,000 məqalə və başlıq cütlüyündən ibarətdir. Üç fərqli model EC2 P2 single GPU - da öyrədilmiş və nəticələri aşağıda göstərilmişdir.

*Digər dillər: [English](README.md)*

Öyrənmə datasını təsdiqləmə və test datası ilə birlikdə aşağıdakı keçidi istifadə edərək yükləyin:

```
$ wget -q https://s3.us-east-2.amazonaws.com/derintelligence/dataset/summarization-data.zip
```

# Rouge dəyərlər
| Model  | R-1 | R-2 | R-L |
| ------------- | ------------- | ------------- | ------------- |
| BOW  | 0.35511  | 0.11384  | 0.32372  |
| Heç biri  | 0.28035  | 0.06750  | 0.24548  |
| Attention(Mul)+BOW  | 0.37022  | 0.11051  | 0.39528  |

# Bəzi empirik nəticələr

**Orijinal məqalə:** bu barədə hərracların son nəticələrinə istinadən xəbər verir .
ice london qitələrarası birjasında brent markalı neftin qiyməti \# , \# \# azalaraq
\# \# , \# dollar olub . nyu-yorkun nymex əmtəə birjasında keçirilən elektron
ticarət əməliyyatlarının son gedişində wti neftinin qiyməti \# barelə görə \# , \#
\# ucuzlaşaraq \# \# , \# \# dollar təşkil edib .   
**Orijinal başlıq:** neft cüzi ucuzlaşdı  
**Att(Mul)+BOW:** neftin qiyməti kəskin düşdü – son qiymətləri davam edir  
**BOW:** brent markalı neftin qiyməti \# bahalaşır – son qiymətləri . .  
**None:** neftin qiyməti qiymətləri düşdü – son yenidən kəskin bahalaşdı + oldu  

**Orijinal məqalə:** \# istinadən verdiyi məlumata görə ,
dünya ulduzları bir araya “ hell energy ” enerji içkilərinin təşkilatçılığı ilə
toplanır . “ hell energy ” nin marketinq direktoru müşfiq <unk> sözlərinə
görə , baş tutacaq konsert proqramında yeni “ hell <unk>fokus ” məhsulu da
təqdim ediləcək : “ konsert proqramında biz yeni “ hell <unk> fokus ” adlı
məhsulumuzu təqdim edəcəyik . bu “ hell ” in yeni bir növüdür . bu məhsul
zehni fəaliyyətlə məşğul olanlara .  
**Orijinal başlıq:** türkiyə rusiya və ukrayna məşhurları azərbaycana gəlir  
**Att(Mul)+BOW:** azərbaycanda yeni konsert təqdim olunub – olunmuş + foto  
**BOW:** “ qarabağ ” ın yeni vəzifə verildi – foto  
**None:** “ iphone ” təqdim etdi – foto + proqnoz ilədayandırdı  
  
# Mənbə

[1. A Neural Attention Model for Abstractive Sentence Summarization - Rush et al.](https://arxiv.org/abs/1509.00685)  
[2. A Neural Attention Model for Abstractive Sentence Summarization - Torch implementation by Facebook research](https://github.com/facebookarchive/NAMAS)
