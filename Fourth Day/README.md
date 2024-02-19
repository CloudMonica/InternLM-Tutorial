### 微调任务（这种分类方式待确认）
- 增量预训练微调：
	- 使用场景：让基座模型学习到一些新知识，如某个垂直领域的常识
	- 训练数据：文章、书籍、代码等
	- 对话模板：通常包含三个角色（System空，User空，Assistant）
- 指令跟随微调：
	- 使用场景：让模型学会对话模板，根据人类指令进行对话
	- 训练数据：高质量的对话、问答数据
	- 对话模板：通常包含三个角色（System，User，Assistant）
	
### 微调资源消耗对比
- Full Finetuning：加载预训练模型所有权重参数，加载模型参数优化器
- LoRA：加载预训练模型所有权重参数，仅加载LoRA小模型的参数优化器
- QLoRA：使用4bit量化加载模型权重参数，参数优化器可以在GPU和CPU之间进行调度

[哔哩哔哩视频链接](https://www.bilibili.com/video/BV1yK4y1B75J/?spm_id_from=333.788&vd_source=830b7af6ec25a6246b75401107901799)  
[git链接](https://github.com/InternLM/tutorial/tree/main/xtuner)  
