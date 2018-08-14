# RDFValidator
method to check if the RDF statementes are valid, if they have a subject/predicate/object form correctly with XML markup

import java.io.FileInputStream;

import org.apache.jena.rdf.model.Model;
import org.apache.jena.rdf.model.ModelFactory;
import org.apache.jena.riot.RDFDataMgr;
import org.apache.jena.riot.RDFFormat;
import org.apache.jena.riot.RDFLanguages;

public class RDFvalidator {
    
    private static final String dataDir = "C:\\Users\\laura\\Documents\\Homework\\Semantic Web\\rdf_file.txt";
    // change the above file path to your own path
    
   public static void main(String[] args) {        
      Model model = ModelFactory.createDefaultModel();
      try {
    
    RDFDataMgr.read(model, new FileInputStream(dataDir), RDFLanguages.RDFXML);
    RDFDataMgr.write(System.out, model, RDFFormat.RDFXML_PRETTY);
      } catch (Exception e) {
    System.out.println("something wrong...");
    e.printStackTrace();
      }
   }
}

