File home = FileSystemView.getFileSystemView().getHomeDirectory();<br>
logger.info("home.getAbsolutePath : " +  home.getAbsolutePath());

또는

String dir = System.getProperty("user.home") + "\\Desktop";

또는

File home = FileSystemView.getFileSystemView().getDefaultDirectory();
				logger.info("path : " + home);

<br>

    // A binary file was returned
    File home = FileSystemView.getFileSystemView().getHomeDirectory(); 
    logger.info("home.getAbsolutePath : " +  home.getAbsolutePath());

    //String dir = System.getProperty("user.home") + "\\Desktop";
    File saveFilePath = null;

    String disposition = conn.getHeaderField("Content-Disposition");
    int index = disposition.indexOf("filename=");

    String name = disposition.substring(index + 10, disposition.length() - 1);
    //saveFilePath = new File(dir, name);
    saveFilePath = new File(home, name);

    InputStream inputStream = conn.getInputStream();
    FileOutputStream outputStream = new FileOutputStream(saveFilePath);

    int bytesRead = -1;
    byte[] buffer = new byte[4096];
    while ((bytesRead = inputStream.read(buffer)) != -1) {
      outputStream.write(buffer, 0, bytesRead);
    }

    outputStream.close();
    inputStream.close();
    logger.info("File downloaded to : " + saveFilePath);

    writer.println("<script>alert('사본 다운로드 성공'); location.href='/eform/form.jsp';</script>");
