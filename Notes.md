- Create a new project with JAVA FX on intellij
- What are the classes that we need

- Change the package name to sudoku
- remove sample.xml
- create a sub package called problem domain

  - Create a SudokuGame class inside this domain
  - private final gamestate gamestate;
  - private final int[][] gridstate;
  - GRID_BOUNDARY = 9;
  - Contructor & getter, gett is copy the grid state
  - SudokuUtilitiles.copyToNewArray(gridState);
  - make sure the calss implements Serializable

- public class Coordinates in same problemDomain package

  - private final x, y;
  - add getters;

  @Overrice

  - public boolean equals (Object o)
    if(this == 0) return true;
    if(0 == null | getClass() != o.getClass()) return false;
    Coordinates that = (Coordinates) 0;
    return x == that.x && y == that.y

  @Override int hashCode(){
  return Objects.hash(x,y);
  }

- Define an interface in the problemDomain package
  interface IStorage
  void updateGameData(SudokuGame game) throws IOException;
  SudokuGame getGameData() throws IOException;
- Package Contants inside sudoku

  - public enum GameState{
    COMPLETE,
    ACTIVE,
    NEW
    }
  - Messages{
    public static final String GAME_COMPLETE="CONGRATUALATIONS, ou have won! new game?"
    public static final String ERROR ="An Error occured ?"
    }
  - public enum ROW{
    TOP,
    MIDDLE,
    BOTTOM
    }

- Rename the MAIN class as SudokuApplication
- Create a MAIN class
  in main method call the sudoku application.main(new String[]{});

- Now SudokuApplication class

  - private IUserInterfaceContract.View uiImpl;
  - Inside start method
    uiImpl = new UserInterfaceImpl(primaryStage);
    try{
    SudokuBuildLogic.build(uiImpl);
    }catch(IOException e){
    e.printStackTrace();
    throw e;
    }
  - Make sure to have main method in this sudoku application class

- Project Structure -> Libraries -> plus icon -> java -> lib folder in java fx sdk

---

create a
