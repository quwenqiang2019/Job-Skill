# langchain
- 尽管大型语言模型的调用相对简单，但要创建完整的应用程序，仍然需要大量的定制开发工作，包括API集成、互动逻辑、数据存储等等。
- LangChain 是一个基于大语言模型的编程框架，主要目标是建立LLM与各种外部数据源之间的连接，可以帮助我们创建基于大语言模型的端到端应用程序或流程。
- LangChain 框架是一个开源工具，充分利用了大型语言模型的强大能力，以便开发各种下游应用。它的目标是为各种大型语言模型应用提供通用接口，从而简化应用程序的开发流程。具体来说，LangChain 框架可以实现数据感知和环境互动，也就是说，它能够让语言模型与其他数据来源连接，并且允许语言模型与其所处的环境进行互动。


- 加载文档：langchain.document_loaders
	- 加载PDF文档
		- from langchain.document_loaders import PyMuPDFLoader
- 文档分割：langchain.text_splitter
	- 按字符来分割文本
		- from langchain.text_splitter import CharacterTextSplitter
- 词嵌入模型：langchain.embeddings
		- from langchain.embeddings.openai import OpenAIEmbeddings
		- from langchain.embeddings.huggingface import HuggingFaceEmbeddings
		- from zhipuai_embedding import ZhipuAIEmbeddings


- 提示：langchain.prompts
		- from langchain.prompts import PromptTemplate
- 智能体：langchain.agents
- 对话模型：langchain.chat_models
		- from langchain.chat_models import ChatOpenAI
- 问答链：langchain.chains
		- from langchain.chains import RetrievalQA
- 记忆：langchain.memory
- 大模型：langchain.llms
		- from langchain.llms import OpenAI
		- from langchain.llms import HuggingFacePipeline
- 回调：langchain.callbacks
- 向量数据库：langchain.vectorstores
		- from langchain.vectorstores import Chroma