# JAVA FX RELATED TROUBLESHOOTING

SHOWING IMAGES ON POPUP EVENT via JAVAFX.   
- Make sure JAVAFX is setup and executing successfully. Refer to JAVAFXSETUP segment of this repository
- import javafx.scene.layout.GridPane;
- import javafx.scene.image.*;
- ^ these two classes are necessary for dealing with images. note that you also have to import other necessary javafx-related classes
- IMPORTANT: paste your photo file into the default package (or just "package") folder NOT into the root folder of everything
    
       
         
DEALING WITH GUI JAVA FX.  
- Make sure on the run configurations:  
  - Add this on the VM arguments (remove <,> symbols and include the two dashes in front):
  --module-path <path/tojavafx/sdk> --add-modules javafx.controls,javafx.fxml  
  - Uncheck these boxes:  
    - Use the -XstartOnFirstThread argument when launching with SWT
    - Use the -XX: +ShowCodeDetailsInExceptionMessages argument when launching
    - Use @argfile when launching
