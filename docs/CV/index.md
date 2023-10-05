<!DOCTYPE html>
<html>
<head>

<title>CV</title>

<style>

/* body {
  display: flex;
  flex-direction: column;
  align-items: center; 
  justify-content: center;
} */

 .pdf-container {
  width: 100%;
  height: 90vh; 
}

@media (min-width: 768px) {
  .pdf-container {
    max-width: 800px; 
    height: 90vh;
  }
}

.divider {
  width: 99%;
  max-width: 800px;
  height: 2px;
  background-color: #ccc;
  margin: 20px 0;
  border: none;
}  

.download-link {
  color: black;
}

</style>

</head>

<body>

<div class="pdf-container">
  <embed src="CV.pdf" type="application/pdf" width="100%" height="100%">  
</div>

<hr class="divider">

<div>
  <a href="CV.pdf" download="个人简历.pdf" class="download-link">下载PDF</a>
</div>

</body>
</html>
