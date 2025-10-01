# Survey Documentation Tool 📊

A full-stack application that processes XML survey files, Q-field metadata, and Alternative Set files to generate comprehensive Excel documentation with professional formatting.

## 🌟 Features

- **📤 File Upload Interface**: Easy drag-and-drop upload for XML, Q-field, and Alternative Set files
- **⚡ Real-time Processing**: FastAPI backend with progress tracking
- **📋 Excel Generation**: Professional formatted Excel output with highlighting and proper structure
- **🎨 Modern UI**: React + TypeScript frontend with TailwindCSS styling
- **✅ Validation**: Comprehensive file validation and error handling
- **📱 Responsive Design**: Works on desktop and mobile devices

## 🏗️ Architecture

```
┌─────────────────┐    HTTP POST     ┌──────────────────┐
│   React Frontend│ ───────────────► │   FastAPI Backend│
│   (Port 3000)   │                  │   (Port 8000)    │
└─────────────────┘                  └──────────────────┘
                                              │
                                              ▼
                                    ┌──────────────────┐
                                    │ Survey Processor │
                                    │   Python Module │
                                    └──────────────────┘
                                              │
                                              ▼
                                    ┌──────────────────┐
                                    │  Excel Generator │
                                    │   (xlsxwriter)   │
                                    └──────────────────┘
```

## 🚀 Quick Start

### Prerequisites
- Node.js 16+ 
- Python 3.8+
- Git

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/survey-documentation-tool.git
cd survey-documentation-tool
```

### 2. Backend Setup
```bash
cd backend
python -m venv venv
venv\Scripts\activate  # Windows
pip install -r requirements.txt
python main.py
```
Backend will run on `http://localhost:8000`

### 3. Frontend Setup
```bash
# In project root
npm install
npm run dev
```
Frontend will run on `http://localhost:3000`

## 📋 Usage

1. **Upload Files**: Upload your XML survey file, Q-field metadata file (.txt), and Alternative Set file (.txt)
2. **Process**: Click "Generate Excel Documentation" to start processing
3. **Download**: Download the generated Excel file with formatted survey documentation

### Required File Types
- **XML Survey File** (`.xml`): Contains survey structure and questions
- **Q-field Metadata File** (`.txt`): Contains question field definitions  
- **Alternative Set File** (`.txt`): Contains answer choice definitions

## 🛠️ Technology Stack

### Frontend
- React 18 + TypeScript
- Vite (build tool)
- TailwindCSS (styling)
- Lucide React (icons)

### Backend  
- FastAPI (Python web framework)
- pandas (data processing)
- xlsxwriter (Excel generation)
- uvicorn (ASGI server)

## 📖 API Documentation

Once the backend is running, visit:
- Health Check: `http://localhost:8000/health`
- API Docs: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

### Main Endpoint
`POST /process-survey-files`
- Accepts: `xml_file`, `q_field_file`, `alt_set_file`
- Returns: Excel file for download

## 🔧 Development

### Project Structure
```
survey-documentation-tool/
├── src/                     # React frontend source
│   ├── pages/SpecificationDoc.tsx
│   ├── components/
│   └── contexts/
├── backend/                 # FastAPI backend
│   ├── main.py             # FastAPI application
│   ├── survey_processor.py # Processing module
│   └── requirements.txt
├── package.json            # Node dependencies
└── README.md
```

### Running in Development
- Frontend: `npm run dev` 
- Backend: `cd backend && python main.py`

## 🚢 Deployment

### Frontend (Vercel/Netlify)
```bash
npm run build
# Deploy dist/ folder
```

### Backend (Railway/Heroku)
```bash
# Use backend/ folder with requirements.txt
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- 📧 Create an [Issue](https://github.com/your-username/survey-documentation-tool/issues)
- 💬 Start a [Discussion](https://github.com/your-username/survey-documentation-tool/discussions)

## 🎯 Roadmap

- [ ] Batch file processing
- [ ] Custom Excel templates
- [ ] Advanced validation rules
- [ ] Export to multiple formats
- [ ] API rate limiting
- [ ] User authentication

---

Made with ❤️ for survey data processing
