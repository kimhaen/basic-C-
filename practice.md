### Write CSV

sample code-
```
```java
private void button10_Click(object sender, EventArgs e)
       {

           string text2 = "CSV出力中、少々お待ちを";
           MessageBox.Show(text2);

           /// <summary>
           /// ファイル保存ダイアログを表示し、ファイル保存先パスを取得する。
           /// </summary>

           string fileName = "テスト" + DateTime.Now.ToString("yyyyMMddHHmmss") + ".csv";
           //string filePath = ShowCsvSaveFolderDialog(fileName);

           SaveFileDialog dlgSaveFile = new SaveFileDialog();
           dlgSaveFile.FileName = fileName;
           string strFirstAppPath = System.Environment.CurrentDirectory;
           dlgSaveFile.InitialDirectory = System.Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);
           dlgSaveFile.Filter = "CSVファイル(*.csv)|*.csv|すべてのファイル(*.*)|*.*";
           dlgSaveFile.CheckFileExists = false;
           dlgSaveFile.RestoreDirectory = true;

           if (dlgSaveFile.ShowDialog() == DialogResult.OK)
           {
               string filePath = dlgSaveFile.FileName;

               if (filePath != null && filePath.Length > 0)
               {
                   System.IO.StreamWriter sr = null;

                   StreamWriter sw = new StreamWriter(filePath, false, Encoding.UTF8);

                   String field = "教科,氏名,クラス名 ";

                   sw.WriteLine(field);

                   string box2txt2 = textBox2.Text;

                   sw.WriteLine(box2txt2);

                   sw.Close();

                   string text3 = "DONE";
                   MessageBox.Show(text3);
               }

               return;
           }

       }

```
