# 项目规则与用户偏好

## 项目信息
- 项目名称: JoyAge悦龄抑郁风险评估平台
- 技术栈: Python, Streamlit, SHAP, scikit-learn
- 目标用户: 45岁以上中老年人群

## 用户偏好
- 语言: 支持中文、英文、韩文三语言切换
- 界面风格: 现代化UI，卡片式布局
- 功能重点: 个性化SHAP解释分析

## 运行要求
- 使用Streamlit运行Web应用
- 确保所有依赖包已安装
- 模型文件需在saved_models目录中

---

## Streamlit Cloud部署检查结果

### ✅ 已解决的问题
1. **配置文件冲突**: 已修复.streamlit/config.toml中的冲突设置
   - 注释掉enableCORS和port设置
   - 移除已弃用的client配置

### ⚠️ 需要注意的问题

#### 1. 文件大小 (✅ 通过)
- cesd_model_best_latest.joblib: 227KB
- cesd_model_best_hyperparameter_tuned_20250809_012713.joblib: 713KB
- 所有文件都在GitHub 100MB限制内

#### 2. 依赖包文件冲突
- **问题**: 存在两个requirements文件
  - requirements.txt (可能缺失)
  - requirements_web.txt (完整)
- **建议**: 重命名requirements_web.txt为requirements.txt

#### 3. 文件路径问题
- **问题**: 应用文件名包含空格 "cesd_web_app_bilingual v2.py"
- **建议**: 重命名为 "cesd_web_app_bilingual_v2.py"

#### 4. 核心模块完整性 (✅ 通过)
- cesd_depression_model模块完整
- 所有必需的.py文件存在
- saved_models目录包含必需的模型文件 