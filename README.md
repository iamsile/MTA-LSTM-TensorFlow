# MTA-LSTM in TensorFlow

TensorFlow implementation of paper [Topic-to-Essay Generation with Neural Networks](http://ir.hit.edu.cn/~xcfeng/xiaocheng%20Feng's%20Homepage_files/final-topic-essay-generation.pdf).

## Motivation: 

The origin [implementation](https://github.com/hit-computer/MTA-LSTM) only provides the MTA-LSTM model, and the code is out-of-date.
In this repo, all three models in the paper are implemented in TensorFlow. And the latest TensorFlow seq2seq and RNNWrapper apis are utilized to make the code clean. 

**If you find this repo is helpful, a star would be so nice!**

## Prerequisites
- Python3
- TensorFlow >= 1.7

## Implementation Notes
1. TAV-LSTM: feed topic embedding average to a forward network to obtain initial state of decoder.
2. TAT-LSTM: at each time step, compute attention on the topic embedding using Bahdanau Attention, and concat with input to the decoder.
3. MTA-LSTM: maintain a **coverage vector** to record the whether topic information has been expressed during the training.

**Note**: beam search used in the origin repo is **NOT SUPPORTED**.

You can refer to the code for more details. If you meet any problems, feel free to raise a issue. 

For the data preprocessing, you may refer to the origin paper and process your own data.



## Generated Examples
Below are some examples  generated by three models (in Chinese):

---

Topic words:  留学 职业规划

TAV-LSTM: 现在 在 一 家 国企 上班 ， 离家 太 远 的 样子 ， 所以 我 想 去 云南 ， 想 去 一 家 公司 工作 ， 但是 我 想 去 外地 工作 ， 我 想 去 大 城市 发展 ， 但是 父母 供 我 见识 ， 我 应该 怎么 做 ？ 人 的 宝宝 应该 怎么 办 ？

TAT-LSTM: 本人 是 211 大学 的 大二 学生 ， 现在 在 湖北 ， 学校 是 五年制 ， 在 湖北 ， 英语 还 行 ， 想 去 学 些 什么 ， 不 想 从事 会计 方面 ， 想 转 专业 的 ， 希望 能 从事 高 学历 的 ， 但是 不 知道 该 做 些 什么 ？ 需要 具备 哪些 方面 的 工作 ？ 是 不 是 也 就 是 这样 的 ， 的 话 ， 应该 如何 选择 ？ 大学 毕业生 ， 在 做 什么 准备 的 ，

MTA-LSTM: 我 是 一 名 大 二 学生 ， 刚 开始 学 德语 ， 英语 也 不好 ， 但是 还是 很 喜欢 数学 ， 不 知道 怎么 分辨 真假 ， 因为 我 是 个 近视 ， 我 想 转 专业 ， 我 想 考 个 证 ， 但是 我 不 知道 怎么 做 ， 我 想 问 一下 ， 有 没 有 什么 建议 和 方法 能够 更 好 的 英语 教育 呢 ？ 希望 能够 得到 各位 的 答案 ， 谢谢 ！ ╰ 我 还有 研究 人员 是 什么 ？ ） 我 想 问 的 是 ： 1.

---

Topic words: 留学 职业规划

TAV-LSTM: 现在 在 一 家 国企 上班 ， 离家 太 远 的 样子 ， 所以 我 想 去 云南 ， 想 去 一 家 公司 工作 ， 但是 我 想 去 外地 工作 ， 我 想 去 大 城市 发展 ， 但是 父母 供 我 见识 ， 我 应该 怎么 做 ？ 人 的 宝宝 应该 怎么 办 ？

TAT-LSTM: 本人 是 211 大学 的 大二 学生 ， 现在 在 湖北 ， 学校 是 五年制 ， 在 湖北 ， 英语 还 行 ， 想 去 学 些 什么 ， 不 想 从事 会计 方面 ， 想 转 专业 的 ， 希望 能 从事 高 学历 的 ， 但是 不 知道 该 做 些 什么 ？ 需要 具备 哪些 方面 的 工作 ？ 是 不 是 也 就 是 这样 的 ， 的 话 ， 应该 如何 选择 ？ 大学 毕业生 ， 在 做 什么 准备 的 ，

MTA-LSTM: 我 是 一 名 大 二 学生 ， 刚 开始 学 德语 ， 英语 也 不好 ， 但是 还是 很 喜欢 数学 ， 不 知道 怎么 分辨 真假 ， 因为 我 是 个 近视 ， 我 想 转 专业 ， 我 想 考 个 证 ， 但是 我 不 知道 怎么 做 ， 我 想 问 一下 ， 有 没 有 什么 建议 和 方法 能够 更 好 的 英语 教育 呢 ？ 希望 能够 得到 各位 的 答案 ， 谢谢 ！ ╰ 我 还有 研究 人员 是 什么 ？ ） 我 想 问 的 是 ： 1.