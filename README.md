# GTDB-Datasets
![CC BY-NC-ND](https://raw.githubusercontent.com/uchidalab/GTDB-Dataset/master/Cc-by-nc-nd_icon.png)

## Introduction
To promote further research into OCR for scientific documents, we releases databases that may be suitable for research outside of InftyProject development. We have carefully scrutinized the data in these releases, and expect that the databases can be relied upon with high confidence. Nevertheless, if you experience any problems with them, please contact us.

The datasets, called GTDB-1 and GTDB-2, consist of document page images collected from scientific journals and textbooks. 
The GTDB-1 dataset contains 31 English articles on mathematics. The GTDB-2 dataset contains 16 articles. Diverse font faces and mathematical notation styles are included in these articles. A list of the articles in both datasets is provided in the bottom of this page.

The statistics of each dataset are shown in the table. The article pages were originally scanned at 600 dpi. The ground truth annotations for each math symbol and ordinary character were attached manually.

Statistics of the datasets

||GTDB-1|GTDB-2|
---:|---:|---:|
Number of articles | 31 | 16 |
Number of pages | 544 | 343 |
Number of math symbols | 162,406 | 115,433|
Number of ordinary text characters | 646,714 | 507,412 |

Here, the ground truth annotation is released. Although we could not include the original document images of articles for copyright reasons, we provide hyperlinks to the web pages of the original documents, where the users can obtain the document images.

## Format of annotation CSV files

Annotations for document pages in one article are provided by one CSV file. The format of CSV files are as following:

    Infty GT-Data Format Ver.1.1
    Sheet,1,AIF_1970_20_493.png,-1
    Text,1,116,411,996,559
    Line,1,118,411,996,471
    Chardata,1,118,416,159,463,0,-1,-1,0141
    Chardata,2,164,428,197,462,0,-1,1,016E
    Chardata,3,201,428,234,461,0,-1,2,016E
    Chardata,4,239,453,249,464,0,-1,3,142E

* The first line is a file header showing the format version.
* Records (lines) starting with `Sheet` denote the beginning of a new page. Each field (column) in `Sheet` record denotes 
`1:Sheet, 2:Page ID, 3:Filename of the page image, 4:always -1`. 
* Records stating with `Text` or `Image` are corresponding to one document layout component. `1:Text or Image, 2:Component ID, 3-6:Coordinates of the bounding box (left, top, right, bottom)`
* Records starting with `Line` denote the text line. `1:Line, 2:Line ID, 3-6:Coordinates of the bounding box (left, top, right, bottom)`
* Records starting with `Chardata` denote the characters or symbols. `1:Chardata, 2:Character ID, 3-6:Coordinates of the bounding box (left, top, right, bottom), 7:Text Mode (0:Ordinary text, 1:Math symbol), 8:Link label, 9:ID of parent character, 10:OCR code`

The number in `Link label` field represents the positional relationship to the preceding character, called parent character.

    0: horizontal
    1: right-superscript
    2: right-subscript
    3: left-superscript
    4: left-subscript
    5: upper
    6: lower
    -1: the first character in expressions or ordinary texts
    
## Conditions of use

GTDB datasets are distributed under CC BY-NC-ND license. Usage for research, development, or testing of OCR systems (not commercial) for scientific documents is permitted, free of charge.

The copyright and license holder of GTDB datasets is  
Masakazu Suzuki:  
[Science Accessibility Net](http://www.sciaccess.net/en/),  
Professor emeritus of Kyushu University

Citation:

W. Ohyama, M. Suzuki and S. Uchida, "Detecting Mathematical Expressions in Scientific Document Images Using a U-Net Trained on a Diverse Dataset," in IEEE Access, vol. 7, pp. 144030-144042, 2019, doi: 10.1109/ACCESS.2019.2945825. [link](https://ieeexplore.ieee.org/document/8861044/references#references)

    @ARTICLE{8861044,
        author={W. {Ohyama} and M. {Suzuki} and S. {Uchida}},
        journal={IEEE Access}, 
        title={Detecting Mathematical Expressions in Scientific Document Images Using a U-Net Trained on a Diverse Dataset}, 
        year={2019},
        volume={7},
        number={},
        pages={144030-144042},
        doi={10.1109/ACCESS.2019.2945825}}

## List of articles

In GTDB-1 dataset
* AIF_1970_493_498.csv: [Ann. Inst. Fourier, 20, 1, 493-498, 1970.](http://aif.cedram.org/aif-bin/item?id=AIF_1970__20_1_493_0)
* AIF_1999_375_404.csv: [Ann. Inst. Fourier, 49, 2, 375-404, 1999.](http://aif.cedram.org/aif-bin/item?id=AIF_1999__49_2_375_0)
* AM_chapter12.csv: [Analytical Mechanics (pp. 493-557). Cambridge Univ. Press, 1998.](https://www.cambridge.org/core/books/analytical-mechanics/special-relativity/283A31E1632C7E028C596DD7F902FC03)
* ASENS_1970_273_284.csv: [Ann. Sci. Ecole Norm. Sup., 4d ser, t.3, 273-284, 1970.](http://www.numdam.org/item/?id=ASENS_1970_4_3_3_273_0)
* ASENS_1970_273_284.csv: [Ann. Sci. Ecole Norm. Sup., 4e ser, t.30, 367-384, 1997.](http://www.numdam.org/item/ASENS_1997_4_30_3_367_0/)
* ActaM_1970_37_63.csv: [Acta Math., 124, 2, 37-63, 1970.](https://projecteuclid.org/euclid.acta/1485889650)
* ActaM_1998_283_305.csv: [Acta Math., 181, 2, 283-305, 1998.](https://projecteuclid.org/euclid.acta/1485891181)
* AnnM_1970_550_569.csv: [Ann. Math., 91, 550-569, 1970.](https://www.jstor.org/stable/1970637?seq=1#metadata_info_tab_contents)
* AnnMS_1971_157_173.csv: [Ann. Math. Studies, 66, 157-173, 1971.](https://press.princeton.edu/titles/13.html)
* Arkiv_1971_141_163.csv: [Arkiv för Matematik, 9(1), 141-163 1971.](https://link.springer.com/article/10.1007/BF02383641)
* Arkiv_1997_185_199.csv: [Arkiv för Matematik, 35, 185-199, 1997.](https://link.springer.com/article/10.1007/BF02559598)
* BAMS_1971_1974.csv: [Bull. Amer. Math. Soc., 77(1), 157-159, 1971](http://www.ams.org/journals/bull/1971-77-01/S0002-9904-1971-12644-7/),  
[ibid., 77(1), 160-163, 1971](http://www.ams.org/journals/bull/1971-77-01/S0002-9904-1971-12646-0/),  
[ibid., 80(6), 1219-1222,1974.](https://www.ams.org/journals/bull/1974-80-06/S0002-9904-1974-13686-4/),  
* BAMS_1998_123_143.csv: [Bull. Amer. Math. Soc., 35(2), 123-143, 1998.](http://www.ams.org/journals/bull/1998-35-02/S0273-0979-98-00745-9/home.html)
* BSMF_1970_165_192.csv: [Bull. Soc. Math. France, 98, 165-192, 1970.](http://www.numdam.org/item/?id=BSMF_1970__98__165_0)
* BSMF_1998_245_271.csv: [Bull. Soc. Math. France, 126, 245-271, 1998.](http://www.numdam.org/item/BSMF_1998__126_2_245_0/)
* InvM_1970_121_134.csv: [Invent. Math., 9, 121-134, 1970.](https://escholarship.org/uc/item/30x2b9n3)
* InvM_1999_163_181.csv: [Invent. Math., 138, 163-181, 1999. ](https://link.springer.com/article/10.1007/s002220050345)
* JMS_1975_281_288.csv: [J. Math. Soc. Japan, 27(2), 281-288, 1975.](https://projecteuclid.org/euclid.jmsj/1240434774)
* JMS_1975_289_293.csv: [J. Math. Soc. Japan, 27(2), 289-293, 1975.](https://projecteuclid.org/euclid.jmsj/1240434775)
* JMS_1975_497_506.csv: [J. Math. Soc. Japan, 27(2), 497-506, 1975.](https://projecteuclid.org/euclid.jmsj/1240434494)
* JMKU_1971_181_194.csv: [J. Math. Kyoto Univ., 11(1), 181-194, 1971](https://projecteuclid.org/euclid.kjm/1250523693)
* JMKU_1971_373_375.csv: [J. Math. Kyoto Univ., 11(1), 373-375, 1971](https://projecteuclid.org/euclid.kjm/1250523653)
* JMKU_1971_377_379.csv: [J. Math. Kyoto Univ., 11(2), 377-379, 1971](https://projecteuclid.org/euclid.kjm/1250523654)
* KJM_1999_17_36.csv: [Kyushu J. Math., 53, 17-36, 1999.](https://www.jstage.jst.go.jp/article/kyushujm/53/1/53_1_17/_article)
* MA_1970_26_38.csv: [Math. Ann., 188, 26-38, 1970.](https://eudml.org/doc/162034)
* MA_1977_275_292.csv: [Math. Ann., 225(3), 275-292, 1977.](https://link.springer.com/content/pdf/10.1007/BF01425243.pdf)
* MA_1999_175_196.csv: [Math. Ann., 315, 175-196, 1999.](https://link.springer.com/article/10.1007/s002080050291)
* TMJ_1973_317_331.csv: [Tohoku Math. J., 25, 317-331, 1973.](https://projecteuclid.org/euclid.tmj/1178241332)
* TMJ_1973_333_338.csv: [Tohoku Math. J., 25, 333-338, 1973.](https://projecteuclid.org/euclid.tmj/1178241333)
* TMJ_1990_163_193.csv: [Tohoku Math. J., 42, 163-193, 1990.](https://projecteuclid.org/euclid.tmj/1178227652)

In GTDB-2 dataset
* Alford94.csv: [Ann. Math., 140, 703-722, 1994.](https://www.jstor.org/stable/2118576?seq=1#metadata_info_tab_contents)
* Bergweiler83.csv: [Bull. Amer. Math. Soc., 28(2), 151-188, 1993.](http://www.ams.org/journals/bull/1993-29-02/S0273-0979-1993-00432-4/) [arxiv.org](https://arxiv.org/abs/math/9310226) In the dataset, page images from arxiv.org are annotated.
* Borcherds86.csv: [Proc. Natl. Acad. Sci. USA, 83, 3068-3071, 1986.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC323452/pdf/pnas00314-0027.pdf)
* Brezis83.csv: [Proc. Amer. Math. Soc., 88(3) 486-490, 1983.](https://www.jstor.org/stable/2044999?seq=1#metadata_info_tab_contents)
* Burstall77.csv: [J. Assoc. Comp. Mach., 24(1) 44-67, 1977.](https://dl.acm.org/citation.cfm?doid=321992.321996)
* Cline88.csv: [J. reine angew. Math. 391, 85-99, 1988.](http://people.virginia.edu/~lls2l/finite_dimensional.pdf)
* Emden76.csv: [J. Assoc. Comp. Mach., 23(4) 733-742, 1976.](https://dl.acm.org/citation.cfm?id=321991)
* Erbe94.csv: [Proc. Amer. Math. Soc., 120(3) 743-748, 1994.](https://www.jstor.org/stable/2160465?seq=1#metadata_info_tab_contents)
* Gidas79.csv: [Commun. Math. Phys. 68, 209-243, 1979.](https://link.springer.com/article/10.1007/BF01221125)
* Jones83.csv: [Invent. math. 72, 1-25, 1983.](https://link.springer.com/content/pdf/10.1007/BF01389127.pdf)
* Katz99.csv: [Bull. Amer. Math. Soc., 36(1), 1-26, 1999.](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.206.1532)
* Kazhdan79.csv: [Invent. math. 53, 165-184, 1979.](https://link.springer.com/content/pdf/10.1007/BF01390031.pdf)
* Kontsevich94.csv: [Commun. Math. Phys. 164(3), 525-562, 1994.](https://projecteuclid.org/euclid.cmp/1104270948) [author's preprint](https://www.ihes.fr/~maxim/TEXTS/WithManinCohFT.pdf) In the dataset, page images from the author's preprint are annotated.
* Li75.csv: [Amer. Math. Mon., 82(10), 985-992, 1975.](https://www.jstor.org/stable/2318254?seq=1#metadata_info_tab_contents)
* Lorentz48.csv: [Acta Math., 80(1), 167-190, 1948.](https://projecteuclid.org/euclid.acta/1485888479)
* Lusztig89.csv: [J. Amer. Math. Soc., 2(3), 599-635, 1989.](https://www.jstor.org/stable/1990945?seq=1#metadata_info_tab_contents)
