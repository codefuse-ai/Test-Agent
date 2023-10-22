# Test-Agent
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/3e7a1418-4a41-487e-81ae-750d621909a1)

<p>
    <a href="https://github.com/codefuse-ai/Test-Agent">
        <img alt="stars" src="https://img.shields.io/github/stars/codefuse-ai/Test-Agent?style=social" />
    </a>
    <a href="https://github.com/codefuse-ai/Test-Agent">
        <img alt="forks" src="https://img.shields.io/github/forks/codefuse-ai/Test-Agent?style=social" />
    </a>
    <a href="https://github.com/codefuse-ai/Test-Agent/LICENCE">
      <img alt="License: MIT" src="https://badgen.net/badge/license/apache2.0/blue" />
    </a>
    <a href="https://github.com/codefuse-ai/Test-Agent/issues">
      <img alt="Open Issues" src="https://img.shields.io/github/issues-raw/codefuse-ai/Test-Agent" />
    </a>
</p>

### 本地Mac M1体验效果



### 魔搭体验效果

## 什么是Test Agent？（Introduction）

**Test Agent** 旨在构建测试领域的“智能体”，融合大模型和质量领域工程化技术，促进质量技术代系升级。我们期望和社区成员一起合作，打造创新的测试领域解决方案，构建24小时在线的测试助理服务，让测试如丝般顺滑。
## 本期特性（Features）

* **模型** 本期我们开源了测试领域模型TestGPT-7B。模型以CodeLlama-7B为基座，进行了相关下游任务的微调：

  * **多语言测试用例生成（Java/Python/Javascript）** 一直以来都是学术界和工业界非常关注的领域，近年来不断有新产品或工具孵化出来，如EvoSuite、Randoop、SmartUnit等。然而传统的用例生成存在其难以解决的痛点问题，基于大模型的测试用例生成在测试用例可读性、测试场景完整度、多语言支持方面都优于传统用例生成工具。本次重点支持了多语言测试用例生成，在我们本次开源的版本中首先包含了Java、Python、Javascript的测试用例生成能力，下一版本中逐步开放Go、C++等语言。
  * **测试用例Assert补全**  对当前测试用例现状的分析与探查时，我们发现代码仓库中存在一定比例的存量测试用例中未包含Assert。没有Assert的测试用例虽然能够在回归过程中执行通过，却无法发现问题。因此我们拓展了测试用例Assert自动补全这一场景。通过该模型能力，结合一定的工程化配套，可以实现对全库测试用例的批量自动补全，智能提升项目质量水位。

* **工程框架** 本地模型快速发布和体验工程化框架

  - ChatBot页面
  - 模型快速启动
  - 私有化部署，本地化的GPT大模型与您的数据和环境进行交互，无数据泄露风险，100%安全

**后续我们会持续迭代模型和工程化能力：**

- 不断加入更多令人激动的测试域应用场景，如领域知识问答、测试场景分析等
- 支撑面向测试场景的copilot 工程框架开放，如测试领域知识智能embedding、测试通用工具API体系、智能测试Agent等，敬请期待！
- 以7B为基础，逐步扩展至13B、34B模型。欢迎关注！

## 性能最强的7B测试领域大模型（Model）
目前在TestAgent中，我们默认使用了TestGPT-7B模型。与当前已有开源模型相比，**TestGPT-7B模型在用例执行通过率（pass@1）、用例场景覆盖（平均测试场景数）上都处于业界领先水平。**
TestGPT-7B模型核心能力的评测结果如下：
- 多语言测试用例生成
针对模型支持的三种语言：Java、Python、Javascript，Pass@1评测结果如下：
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/2115cdaf-9cad-466f-96b7-d742f56d1185)

- 测试用例Assert补全
目前模型支持Java用例的Assert补全，Pass@1评测结果如下：
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/dc4967ec-29d2-4a69-a42c-b7be91503956)

## 工程架构（Engineering Architecture）
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/105af447-1604-4c8a-9f78-8ebfe1f5fac3)

大模型的号角已经吹响，测试领域大模型也在不断进化中，通过预训练过程中积累的丰富世界知识，在复杂交互环境中展现出了非凡的推理与决策能力。

尽管在测试领域中基础模型取得了显著的成果，但仍然存在一些局限性，特定领域的测试任务通常需要专业化的工具或领域知识来解决。例如，基础模型可以通过预训练知识完成单次测试代码生成和测试文本生成等任务，但处理复杂的集成用例生成、特定领域用例生成和测试流程pipeline交互等问题时，需要更专业的工具和领域知识。

因此将专用工具与基础模型整合在一起，可以充分发挥它们各自的优势。专用工具可以解决模型时效性不足、增强专业知识、提高可解释性和鲁棒性的问题。而基础模型则具备类人的推理规划能力，可以理解复杂的数据和场景，并与现实世界进行交互。

在本期开放模型工程化部署和ChatBot基础上，我们将继续在测试开源领域深耕投入。协同社区志趣相投开发者们，一起打造测试领域最领先的Tools工程体系、智能测试助理和测试开源工程！

## 快速使用（QuickStart）
### 前置准备

#### 模型下载

您可在[modelscope](https://modelscope.cn/models/codefuse-ai/TestGPT-7B)或[huggingface](https://huggingface.co/codefuse-ai/TestGPT-7B)上获取到模型的详细信息并下载模型文件。

#### 环境安装

```plain
git clone https://github.com/...
cd TestGPT
pip install -r requirements.txt
```

在开始运行TestGPT-7B模型之前，请确保你的执行环境拥有大约14GB的显存。
### 启动服务

项目提供了网页端快速搭建UI的能力能够更直观的展示模型交互和效果，我们可以使用简单的几个命令把前端页面唤醒并实时调用模型能力。在项目目录下，依次启动以下服务：

1.**启动controller**
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/07de46ec-18f3-457b-814b-b1650b11345a)

python3 -m chat.server.controller

2.**启动模型worker**

python3 -m chat.server.model_worker --model-path models/testgpt --device mps
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/b84ffc6e-be6f-47f6-8f84-b2360fe7b6bc)

对于启动方式，可以按需选择以下几种配置选项：

- --device mps 用于在Mac电脑上开启GPU加速的选项（Apple Silicon或AMD GPUs）；
- --device xpu 用于在Intel XPU上开启加速的选项（Intel Data Center and Arc A-Series GPUs）；
  - 需安装[Intel Extension for PyTorch](https://intel.github.io/intel-extension-for-pytorch/xpu/latest/tutorials/installation.html)
  - 设置OneAPI环境变量：source /opt/intel/oneapi/setvars.sh

- --device npu 用于在华为AI处理器上开启加速的选项；
  - 需安装[Ascend PyTorch Adapter](https://github.com/Ascend/pytorch)
  - 设置CANN环境变量：source /usr/local/Ascend/ascend-toolkit/set_env.sh

- --device cpu 单独使用CPU运行的选项，不需要GPU；
- --num-gpus 2 指定并发gpu运行的选项。

3. **启动web服务**

python3 -m chat.server.gradio_testgpt
![image](https://github.com/codefuse-ai/Test-Agent/assets/103973989/cd7eefa2-a98d-47d2-ac61-04f4e029421b)

待服务准备就绪后，我们可以打开本地启动的web服务地址 http://0.0.0.0:7860 ，就能看到完整的前端页面了。在页面下方包含了【单测生成】和【Assert补全】的两个例子，点击按钮后会自动生成一段样例文本到输入框中，点击Send按钮就会触发模型运行，之后耐心等待一段时间后（运行时间视本机性能而定）即可看到完整的回答了。


