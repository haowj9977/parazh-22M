# ParaZh-22M
A Chinese parabank.


## Download
* [Baidu Netdisk](https://pan.baidu.com/s/1Tc0yYojHdFFVl6gIYeGeiQ) download in Baidu Netdisk(pwd=5bml). 

## Files
8 files in total.

parazh.7z include 6 files: 

* src.train.bpe and tgt.train.bpe contain 22M sentence pairs, each sentence at same line of this two files constitute a pair.

* src.dev.bpe and tgt.dev.bpe contain 10k sentence pairs.

* src.test.bpe and tgt.test.bpe contain 10k sentence pairs.

zh.vcb.bpe and zh.cds is used for BPE.

## Scripts
Each file is performed BPE with 32k merge operation by subword-nmt:
```bash
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < src.train > src.train.bpe
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < tgt.train > tgt.train.bpe

subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < src.dev > src.dev.bpe
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < tgt.dev > tgt.dev.bpe

subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < src.test > src.test.bpe
subword-nmt apply-bpe -c zh.cds --vocabulary zh.vcb.bpe --vocabulary-threshold 8 < tgt.test > tgt.test.bpe

```

You can apply de-BPE by:
```bash
sed -r 's/(@@ )|(@@ ?$)//g' < src.dev.bpe > src.dev
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