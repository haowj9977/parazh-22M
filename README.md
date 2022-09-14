# ParaZh-22M
A Chinese parabank.


## Download
* [Baidu Netdisk](https://pan.baidu.com/s/1htji52Qu7f1FwQFir94CgA) download in Baidu Netdisk(pwd=yrlv). 


## Files
 5 files in total.

parazh.7z include 3 files: 

* tgt.para and out.para contain 22M sentence pairs, sentences at the same line of this two files constitute a pair.

* each line in dis.para is the edit distance ratio (the edit distance divided by the number of tokens).

zh.vcb.bpe and zh.cds is used for BPE (32k merge operation).

## Scripts
You can perform BPE with 32k merge operation by subword-nmt:
```bash
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < tgt.para > tgt.para.bpe
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < out.para > out.para.bpe

```

## Citation
If you use our dataset, we'd appreciate if you cite the following paper:
```
@inproceedings{hao2022parazh-22M,
  title={ParaZh-22M: a Large-Scale Chinese Parabank via Machine Translation},
  author={Wenjie Hao, Hongfei Xu, Deyi Xiong, Hongying Zan and Lingling Mu},
  booktitle={Proceedings of the 29th International Conference on Computational Linguistics (COLING)},
  year={2022}
}
```
