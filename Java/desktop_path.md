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
    
    
    
    				// A binary file was returned
				String disposition = conn.getHeaderField("Content-Disposition");
				int index = disposition.indexOf("filename=");
				String name = disposition.substring(index + 10, disposition.length() - 1);
				
				byte b[] = new byte[4096];

				response.reset();
				response.setContentType("application/octet-stream");

				String Encoding = new String(name.getBytes("UTF-8"), "8859_1");
				response.setHeader("Content-Disposition", "attatchment; filename = " + Encoding);

				InputStream is = conn.getInputStream();
				ServletOutputStream sos = response.getOutputStream();

				int numRead;
				while((numRead = is.read(b,0,b.length)) != -1){
					sos.write(b,0,numRead);
				}

				sos.flush();
				sos.close();
				is.close();
    
    
    
    ref http://www.gnujava.com/board/article_view.jsp?article_no=6509&menu_cd=16&board_no=3&table_cd=EPAR01&table_no=01
