# ParaZh-22M
A Chinese parabank.


## Download
* [Baidu Netdisk](https://pan.baidu.com/s/1htji52Qu7f1FwQFir94CgA) download in Baidu Netdisk(pwd=yr1v). 


## Files
 5 files in total.

parazh.7z include 3 files: 

* tgt.para and out.para contain 22M sentence pairs, sentences at the same line of this two files constitute a pair.

* each line in dis.para is the edit distance ratio (the edit distance divided by the number of tokens).

zh.vcb.bpe and zh.cds are used for BPE (32k merge operations).

## Scripts
You can perform BPE with 32k merge operations by subword-nmt:
```bash
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < tgt.para > tgt.para.bpe
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < out.para > out.para.bpe

```

## Citation
If you use our dataset, we'd appreciate if you cite the following paper:
```
@inproceedings{hao-etal-2022-parazh,
    title = "{P}ara{Z}h-22{M}: A Large-Scale {C}hinese Parabank via Machine Translation",
    author = "Hao, Wenjie  and
      Xu, Hongfei  and
      Xiong, Deyi  and
      Zan, Hongying  and
      Mu, Lingling",
    booktitle = "Proceedings of the 29th International Conference on Computational Linguistics",
    year = "2022",
    address = "Gyeongju, Republic of Korea",
    publisher = "International Committee on Computational Linguistics",
    url = "https://aclanthology.org/2022.coling-1.341",
    pages = "3885--3897",
}

```
