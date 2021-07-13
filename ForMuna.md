# For Muna

1.) Create new file the way you usually start your projects
2.) Right click on the entire folder (the one with a capital J and a folder icon)
3.) Build path -> Configure build path -> Libraries -> press modulepath -> add library -> user library -> select your compatible javafx to your java jre version
4.) Run Configurations -> Arguments -> Under VM arguments: paste the following
--module-path PATH/TO/JAVAFX/SDK/LIB --add-modules javafx.controls,javafx.fxml
