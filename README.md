# passgate

**按门槛判定每项评测是否通过并给出余量。**

`passgate` —— 对照设定的通过率门槛逐项判定，给出距离门槛的余量

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`passgate.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install iza-mine-passgate
```

装完直接用命令名调用：

```bash
passgate --help
```

也可以不用安装，直接把 `passgate.py` 拷走用——它只依赖标准库。

## 为什么需要它

余量是带符号的，接近门槛的项目会被标成临界

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测通过率门槛 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python passgate.py --file input.txt
python passgate.py --text "示例内容"
python passgate.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 阈值是固定值，不随数据自适应。
- 只判定达标与否，不解释分数来源。

## 跑测试

```bash
python test_passgate.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/iza-mine/passgate>

---

## 关于作者

iza-mine 做评测通过率门槛相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://iza-mine.github.io>
- 仓库：<https://github.com/iza-mine/passgate>

## 许可

MIT，见 [LICENSE](LICENSE)。
