# 安装

## 最简方式

直接使用 pip 安装，但有可能由于本地 python 环境依赖库紊乱而导致脚本运行出错。

```bash
pip install -U poseidon-python
```



## 推荐方式

基于 [模板库](https://github.com/B1ue1nWh1te/PoseidonTemplate) 使用 poetry 创建虚拟环境，这样可以保证脚本运行环境干净，减少出现意外错误的可能。

安装 poetry 虚拟环境管理工具（如果之前未安装）：

```bash
pip install -U poetry
```

克隆 [模板库](https://github.com/B1ue1nWh1te/PoseidonTemplate) 至本地（也可先使用该模板库创建一个副本至你自己的 Github 仓库中再克隆）：

```bash
git clone git@github.com:B1ue1nWh1te/PoseidonTemplate.git
```

切换至模板仓库目录并安装虚拟环境：

```bash
cd PoseidonTemplate
poetry install
```

之后假设你编写了一个名为 main.py 的脚本要运行：

```bash
poetry shell
python main.py
```

