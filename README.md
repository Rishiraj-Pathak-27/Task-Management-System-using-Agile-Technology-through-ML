# 🧠 AI Powered Task Management & Assignment System

A self-learning task assignment engine that automatically optimizes team productivity by learning from real task completion results.

## 🎯 What This System Does

- **Enter People & Tasks**: Add team members and work items
- **AI Decides Assignments**: Optimal matching based on learned patterns  
- **System Learns**: From real completion results (time, quality)
- **Gets Smarter**: Continuous improvement with each task

## ✨ Key Features

- **Zero-bias assignments** based on real performance data
- **Universal application** - works for any task type (coding, design, research, etc.)
- **Real-time progress tracking** with notes and updates
- **Automatic skill discovery** - learns who's good at what
- **Burnout prevention** through workload analysis
- **Self-improving AI** that gets better with more data

## 🚀 How to Use

1. **Add Users**: Start with your team members
2. **Add Tasks**: Enter work items with complexity (0-1) and deadline (hours)
3. **Get Assignments**: AI recommends optimal person for each task
4. **Track Progress**: Update task progress and add notes
5. **Complete Tasks**: Enter time taken and quality score (1-5)
6. **Retrain AI**: System learns and improves future assignments

## 🧠 The Learning Process

Initially assigns tasks randomly (no data), but learns from every completion:
- User skill patterns
- Task complexity preferences  
- Time efficiency trends
- Quality consistency
- Workload capacity

## 📊 Real-World Applications

- **Software Teams**: Frontend, backend, testing assignments
- **Study Groups**: Subject-based task distribution
- **Project Management**: Optimal resource allocation
- **Any Team Environment**: Universal skill-based matching

## 🔄 Self-Learning Cycle

```
Add People & Tasks → AI Assigns → Work Completed → 
Enter Results → AI Learns → Better Assignments
```

**Result**: Maximum efficiency, minimum burnout, automatic skill discovery.

## 🛠️ Technical Details

- **AI Model**: Random Forest Regressor (scikit-learn)
- **Features**: User ID, task complexity, deadline pressure
- **Target**: Success score (quality × efficiency)
- **Framework**: Gradio for web interface
- **Data**: CSV files for users, tasks, results, JSON for progress tracking

## 📁 Project Structure & Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      app.py (Web UI)                        │
│                   Gradio Interface - 9 Tabs                 │
└─────────────────────────┬───────────────────────────────────┘
                          │ calls
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                 task_manager.py (Controller)                │
│        Orchestrates all operations & data management        │
└─────────────────────────┬───────────────────────────────────┘
                          │ uses
                          ▼
┌─────────────────────────────────────────────────────────────┐
│              assignment_engine.py (AI Brain)                │
│         RandomForest ML Model for smart assignments         │
└─────────────────────────┬───────────────────────────────────┘
                          │ reads/writes
          ┌───────────────┼───────────────┬───────────────┐
          ▼               ▼               ▼               ▼
    ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────────┐
    │users.csv │   │tasks.csv │   │results.csv│  │task_progress │
    │          │   │          │   │ (AI learns│   │    .json     │
    │Team list │   │Work items│   │ from this)│   │Live tracking │
    └──────────┘   └──────────┘   └──────────┘   └──────────────┘
```

### 🔄 How It All Works Together

1. **You interact** with `app.py` (web interface)
2. **app.py calls** `task_manager.py` functions
3. **task_manager.py uses** `assignment_engine.py` for AI operations
4. **Data is stored** in CSV files (users, tasks, results)
5. **AI learns** from `results.csv` to improve future assignments

# Access the Model: https://huggingface.co/spaces/rishirajpathak/task-management
