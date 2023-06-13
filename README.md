# Farm-Managment-CRUD-App

## Overview

Jeremiah Clarksen, the world renown British car commentator turned farmer in the quaint
English countryside, sets focus of his next venture to the vast land of opportunities on the other side of the Atlantic known as the American Midwest. Confident from his successes garnered through hard work back home, he is determined to single-handedly capture the hearts and minds of American fans, only with a little help from his fellow distributors and a database-powered website that records pertinent information of his farms, equipment, crops, and gift shop orders and customers. The secret to his stateside success, which none other than himself or his distributors shall ever know, is that he will neither own a farm nor participate in the farming operation himself; instead, he will resell produce sourced from his subsidiary farms elsewhere in the nation and rebranded as his very own harvest. Despite locating himself in the sparsely populated middle of nowhere, Jeremiah expects to own and/or track at least 500 items for each entity and record $9 million in sales for the first fiscal year, all of which the system is perfectly capable of.

This project intends to be the one-stop-shop database manager for all prospective farmers yearning to keep track of their farms, equipment, crops, and every data related to sales of its products, such as customer and order information. The conception of this project is greatly attributed to our infatuation with a program widely popular in a major streaming platform, where a famous British car commentator suddenly decides to start a farm in the English countryside, and unsurprisingly faces a myriad of challenges. We wanted to help out any fellow farmers that may be facing similar problems; hence, the project was born.

## Database Outline

### Farms
<ul>
<li>Description: The heart of the action, where the growing of all crops take place, grown and harvested all by Jeremiah... at least on appearance, that is. One farm will exclusively produce one crop, and each farm is maintained by one or many equipment. The database will manage a collection of such farms.</li>
</ul>
<li>Attributes:</li>
<ul>
<li>farm_id, PK, INT, auto_increment, not NULL</li>
<li>farm_name, VARCHAR(255), not NULL</li>
<li>acres, DECIMAL(10, 2), not NULL</li>
<li>address, VARCHAR(255), not NULL</li>
<li>description, VARCHAR(255), not NULL</li>
</ul>

<li>Relationships:</li>
<ul>
<li>1:1 with Crops. One farm will only grow one crop, and one crop can only
be sourced from one farm.</li>
<li>1:M with Equipments. One farm may be maintained by many equipment,
but one equipment will solely be used by one farm.</li>
</ul>

### Equipments
<ul>
<li>Description: Stores all kinds of equipment ranging from tractors to fertilizers. Any given equipment will only belong to one farm but many equipment may be used to maintain a single farm. Equipment cost and value fields are set to keep track of purchase price and the expected value in the event the equipment is no longer necessary and better off sold. An optional maintenance date field will store the next future date a necessary maintenance should take place.</li>
<li>Attributes:</li>
<ul>
<li>equipment_id, PK, INT, auto_increment, not NULL</li>
<li>farm_id, FK, INT, not NULL</li>
<li>purchase_date, DATE, not NULL</li>
<li>equipment_cost, DECIMAL(10, 2), not NULL</li>
<li>equipment_value, DECIMAL(10, 2), not NULL</li>
<li>maintenance_date, DATE</li>
</ul>
<li>Relationships:</li>
<li>M:1 with Farms. Many equipment may be used to maintain one farm, but
one equipment will only belong to one farm.</li>
</ul>