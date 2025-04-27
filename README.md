# Tejas<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tej Background Remover - Professional Image Background Removal Tool</title>
    <style>
        :root {
            --primary-color: #4a6bff;
            --secondary-color: #f8f9fa;
            --accent-color: #ff6b6b;
            --dark-color: #343a40;
            --light-color: #ffffff;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--secondary-color);
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            padding: 40px 0;
            background: linear-gradient(135deg, var(--primary-color), #6c5ce7);
            color: var(--light-color);
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: var(--shadow);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .tagline {
            font-size: 1.2rem;
            opacity: 0.9;
        }
        
        .tool-container {
            background-color: var(--light-color);
            border-radius: 10px;
            padding: 30px;
            box-shadow: var(--shadow);
            margin-bottom: 30px;
        }
        
        .upload-area {
            border: 2px dashed #ccc;
            border-radius: 8px;
            padding: 40px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            margin-bottom: 20px;
            position: relative;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        .upload-area:hover {
            border-color: var(--primary-color);
            background-color: rgba(74, 107, 255, 0.05);
        }
        
        .upload-icon {
            font-size: 48px;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        
        .upload-text {
            font-size: 1.1rem;
            margin-bottom: 10px;
        }
        
        .upload-subtext {
            font-size: 0.9rem;
            color: #666;
        }
        
        #fileInput {
            display: none;
        }
        
        .btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .btn:hover {
            background-color: #3a5bef;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
        }
        
        .btn-secondary {
            background-color: var(--dark-color);
        }
        
        .btn-secondary:hover {
            background-color: #23272b;
        }
        
        .btn-accent {
            background-color: var(--accent-color);
        }
        
        .btn-accent:hover {
            background-color: #e05555;
        }
        
        .btn:disabled {
            background-color: #ccc;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }
        
        .action-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 20px;
        }
        
        .preview-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 30px;
            justify-content: center;
        }
        
        .preview-box {
            flex: 1;
            min-width: 300px;
            text-align: center;
        }
        
        .preview-title {
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        .image-preview {
            max-width: 100%;
            max-height: 400px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            display: none;
        }
        
        .loading {
            display: none;
            text-align: center;
            margin: 20px 0;
        }
        
        .spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            border-radius: 50%;
            border-top: 4px solid var(--primary-color);
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto 15px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        .feature-card {
            background-color: var(--light-color);
            padding: 25px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            text-align: center;
        }
        
        .feature-icon {
            font-size: 36px;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        
        .feature-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        .feature-desc {
            color: #666;
            font-size: 0.95rem;
        }
        
        footer {
            text-align: center;
            padding: 30px 0;
            color: #666;
            font-size: 0.9rem;
        }
        
        .download-options {
            display: none;
            margin-top: 20px;
            text-align: center;
        }
        
        .download-btn {
            margin: 5px;
            padding: 8px 16px;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .tagline {
                font-size: 1rem;
            }
            
            .action-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
                margin-bottom: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Tej Background Remover</h1>
            <p class="tagline">Remove backgrounds from images automatically in seconds</p>
        </header>
        
        <div class="tool-container">
            <div id="uploadArea" class="upload-area">
                <div class="upload-icon">📁</div>
                <div class="upload-text">Drag & drop your image here or click to browse</div>
                <div class="upload-subtext">Supports JPG, PNG, and WEBP (Max 5MB)</div>
                <input type="file" id="fileInput" accept="image/*">
            </div>
            
            <div class="action-buttons">
                <button id="removeBgBtn" class="btn" disabled>Remove Background</button>
                <button id="resetBtn" class="btn btn-secondary" disabled>Reset</button>
            </div>
            
            <div id="loading" class="loading">
                <div class="spinner"></div>
                <p>Removing background... Please wait</p>
            </div>
            
            <div class="preview-container">
                <div class="preview-box">
                    <div class="preview-title">Original Image</div>
                    <img id="originalPreview" class="image-preview" alt="Original image preview">
                </div>
                <div class="preview-box">
                    <div class="preview-title">Background Removed</div>
                    <img id="resultPreview" class="image-preview" alt="Result preview">
                </div>
            </div>
            
            <div id="downloadOptions" class="download-options">
                <p>Download your image:</p>
                <button class="btn download-btn">PNG</button>
                <button class="btn download-btn">JPG</button>
                <button class="btn download-btn">WEBP</button>
            </div>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3 class="feature-title">Instant Processing</h3>
                <p class="feature-desc">Our AI removes backgrounds in seconds with just one click.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎯</div>
                <h3 class="feature-title">Precise Edges</h3>
                <p class="feature-desc">Get clean, sharp cutouts with perfect edges every time.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔒</div>
                <h3 class="feature-title">Privacy Focused</h3>
                <p class="feature-desc">Your images are processed securely and never stored.</p>
            </div>
        </div>
    </div>
    
    <footer>
        <p>© 2023 Tej Background Remover. All rights reserved.</p>
    </footer>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const uploadArea = document.getElementById('uploadArea');
            const fileInput = document.getElementById('fileInput');
            const originalPreview = document.getElementById('originalPreview');
            const resultPreview = document.getElementById('resultPreview');
            const removeBgBtn = document.getElementById('removeBgBtn');
            const resetBtn = document.getElementById('resetBtn');
            const loading = document.getElementById('loading');
            const downloadOptions = document.getElementById('downloadOptions');
            
            let uploadedImage = null;
            
            // Handle click on upload area
            uploadArea.addEventListener('click', function() {
                fileInput.click();
            });
            
            // Handle drag and drop
            uploadArea.addEventListener('dragover', function(e) {
                e.preventDefault();
                uploadArea.style.borderColor = var('--primary-color');
                uploadArea.style.backgroundColor = 'rgba(74, 107, 255, 0.1)';
            });
            
            uploadArea.addEventListener('dragleave', function() {
                uploadArea.style.borderColor = '#ccc';
                uploadArea.style.backgroundColor = '';
            });
            
            uploadArea.addEventListener('drop', function(e) {
                e.preventDefault();
                uploadArea.style.borderColor = '#ccc';
                uploadArea.style.backgroundColor = '';
                
                if (e.dataTransfer.files.length) {
                    fileInput.files = e.dataTransfer.files;
                    handleFileSelect(e.dataTransfer.files[0]);
                }
            });
            
            // Handle file selection
            fileInput.addEventListener('change', function() {
                if (fileInput.files.length) {
                    handleFileSelect(fileInput.files[0]);
                }
            });
            
            function handleFileSelect(file) {
                // Check if file is an image
                if (!file.type.match('image.*')) {
                    alert('Please select an image file (JPG, PNG, or WEBP)');
                    return;
                }
                
                // Check file size (5MB max)
                if (file.size > 5 * 1024 * 1024) {
                    alert('File size exceeds 5MB limit');
                    return;
                }
                
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    uploadedImage = e.target.result;
                    originalPreview.src = uploadedImage;
                    originalPreview.style.display = 'block';
                    
                    // Enable buttons
                    removeBgBtn.disabled = false;
                    resetBtn.disabled = false;
                    
                    // Hide result preview if shown
                    resultPreview.style.display = 'none';
                    downloadOptions.style.display = 'none';
                    
                    // Update upload area text
                    document.querySelector('.upload-text').textContent = file.name;
                    document.querySelector('.upload-subtext').textContent = 
                        `${(file.size / 1024).toFixed(1)} KB | ${file.type.split('/')[1].toUpperCase()}`;
                };
                
                reader.readAsDataURL(file);
            }
            
            // Handle remove background button
            removeBgBtn.addEventListener('click', function() {
                if (!uploadedImage) return;
                
                // Show loading
                loading.style.display = 'block';
                
                // Simulate background removal (in a real app, this would call an API)
                setTimeout(function() {
                    // For demo purposes, we'll just show the same image with a checkerboard pattern
                    // In a real implementation, you would receive the processed image from an API
                    resultPreview.src = uploadedImage;
                    resultPreview.style.display = 'block';
                    loading.style.display = 'none';
                    downloadOptions.style.display = 'block';
                    
                    // Scroll to results
                    resultPreview.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
                }, 2000);
            });
            
            // Handle reset button
            resetBtn.addEventListener('click', function() {
                // Reset everything
                fileInput.value = '';
                originalPreview.src = '';
                originalPreview.style.display = 'none';
                resultPreview.src = '';
                resultPreview.style.display = 'none';
                loading.style.display = 'none';
                downloadOptions.style.display = 'none';
                removeBgBtn.disabled = true;
                resetBtn.disabled = true;
                uploadedImage = null;
                
                // Reset upload area text
                document.querySelector('.upload-text').textContent = 'Drag & drop your image here or click to browse';
                document.querySelector('.upload-subtext').textContent = 'Supports JPG, PNG, and WEBP (Max 5MB)';
            });
            
            // Handle download buttons
            document.querySelectorAll('.download-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    if (!resultPreview.src) return;
                    
                    // In a real implementation, this would download the processed image
                    alert(`In a real implementation, this would download the ${btn.textContent} version`);
                });
            });
        });
    </script>
</body>
</html>
