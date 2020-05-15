# PS01
import { print, promptNumber, promptString } from "introcs";
export let main = async () => {
    // TODO: Put all of your code here
    let alive = true;
    let thirstLevel = 50;
    let bearLikeliness = 50;
    let isHarvestTime = false;
    let day = 0;
    let beetsCount = 10;
    while ( alive && !isHarvestTime) {
        print ("Day: " + day);
        day = day + 1;
        let waterSprayOrHarvest = await promptString ("Do you want to water, spray, or harvest your " + beetsCount + " beets? Type 'water', 'spray', or 'harvest'.");
        if (waterSprayOrHarvest === "water") {
            print (beetsCount + " beets have been watered!");
            beetsCount = beetsCount + 2;
            
            thirstLevel = thirstLevel - 10;
           
            bearLikeliness = bearLikeliness + 10;
            
           
        }
        if (waterSprayOrHarvest === "spray") {
            print (beetsCount + " beets have been sprayed!");
            thirstLevel = thirstLevel + 10;
            
            bearLikeliness = bearLikeliness - 5;
            
        }   
        if (waterSprayOrHarvest === "harvest") {
            print (beetsCount + " beets have been harvested!");
            print ("Your " + beetsCount + " beets were harvested after " + day + " days :)");
            alive = false;
        }
        if (waterSprayOrHarvest !== "water") {
        if (waterSprayOrHarvest !== "spray") {
        if (waterSprayOrHarvest !== "harvest") {
            print (beetsCount + " beets were not watered, sprayed, or harvested.");
            thirstLevel = thirstLevel + 10;
            bearLikeliness = bearLikeliness + 10;
            
        }
        }
        }
        if (thirstLevel <= 0) {
            print ("Your " + beetsCount + " beets have been overwatered");
            print ("This means that " + beetsCount + " beets have died after " + day + " days :(" );
            alive = false;
        } 
        if (thirstLevel > 100) {
            print ("Your " + beetsCount + " beets have been dehydrated!");
            print ("This means that " + beetsCount + " beets have died after " + day + " days :(");
            alive = false;
        }
        if (bearLikeliness >= 100) {
            print ("Your " + beetsCount + " beets were eaten by bears");
            print ("This means that " + beetsCount + " beets have died after " + day + " days :(");
            alive = false;
        }
        if (alive === true) {
            print ("Your " + beetsCount + " beets are alive!");
            print ("Thirst Level of " + beetsCount + " beets: " + thirstLevel);
            print ("Likeliness of Bear Attack of " + beetsCount + " beets: " + bearLikeliness);
        }
        
    }
};
main ();
