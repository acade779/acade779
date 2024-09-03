# 安装streamlit：pip install streamlit
import streamlit as st

# 设置标题
st.title("英语水平测试")

# 听力测试
st.header("听力测试")
st.write("请听以下音频片段，然后回答问题。")
st.audio("https://www.example.com/audio.mp3")  # 替换为实际音频链接
st.write("1. 这段对话的主要话题是什么？")
listening_q1 = st.text_input("请输入你的答案：")

st.write("2. 列出对话中提到的两个重要细节。")
listening_q2 = st.text_input("请输入你的答案：")

# 阅读测试
st.header("阅读测试")
st.write("请阅读以下短文，然后回答问题。")
st.write("Climate change is one of the most pressing issues of our time...")
st.write("1. 这篇文章的主旨是什么？")
reading_q1 = st.text_input("请输入你的答案：")

# 写作测试
st.header("写作测试")
st.write("请从以下题目中选择一个，并写一篇200-300字的短文。")
writing_topic = st.selectbox("请选择一个题目：", 
                             ["描述一个你最近去过的地方，谈谈你的感受和体验。",
                              "讨论你认为科技在未来的教育中将扮演什么样的角色。",
                              "写一封给你朋友的邮件，谈谈你最近的一次有趣的经历。"])
writing_answer = st.text_area("请输入你的作文：")

# 语法和词汇测试
st.header("语法和词汇测试")
st.write("选择正确的选项来完成下面的句子：")
grammar_q1 = st.radio("She ______ a lot of experience in this field.", ("has", "have"))
grammar_q2 = st.radio("If I ______ you, I would definitely go for it.", ("was", "were"))

# 提交按钮
if st.button("提交测试"):
    st.write("感谢你的提交！以下是你的回答：")
    st.write("听力测试 - 问题1:", listening_q1)
    st.write("听力测试 - 问题2:", listening_q2)
    st.write("阅读测试 - 问题1:", reading_q1)
    st.write("写作测试:", writing_answer)
    st.write("语法和词汇测试 - 问题1:", grammar_q1)
    st.write("语法和词汇测试 - 问题2:", grammar_q2)
