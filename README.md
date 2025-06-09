# kuku
舆情分析技术趋势报告
## 技术背景
- 传统舆情分析方法：基于关键词匹配和简单统计。
- 大模型技术：利用深度学习模型理解文本语义。

## 应用场景
1. **社交媒体监测**
2. **危机预警**
from transformers import pipeline

# 加载预训练情感分析模型（基于RoBERTa）
sentiment_analyzer = pipeline("text-classification", model="nlptown/bert-base-multilingual-uncased-sentiment")

# 输入文本（支持多语言，如中文、英文混合）
text = "这款手机的摄像头效果太棒了！不过充电速度有点慢，希望下一代改进～"

# 情感分析
results = sentiment_analyzer(text)
for result in results:
    print(f"情感标签：{result['label']}，置信度：{result['score']:.4f}")

# 输出示例：
# 情感标签：5 stars，置信度：0.8923 （注：模型将情感量化为1-5星，5星为最高正向）
