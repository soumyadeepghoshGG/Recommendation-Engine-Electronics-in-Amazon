
# Introduction to Recommendation systems
Recommendation systems, also known as recommendation engines, are algorithms designed to suggest relevant items to users. In this modern world we are overloaded with data and content but everything is not relevant to a person. Recommendation systems try to understand a person's preferences and behavior, to provide personalized recommendations.
<p>Recommendation systems are widely used in media platforms like Netflix to suggest movies and TV shows, Spotify to suggest music, and e-commerce sites like Amazon to suggest products to customers. </p>

**What recommendation systems can solve?**
1. It can help the user to find the right product.
2. It can increase the user engagement. For example, there's 40% more click on the google news due to recommendation.
3. It helps the item providers to deliver the items to the right user. In Amazon, 35% products get sold due to recommendation.
4. It helps to make the contents more personalized. In Netflix most of the rented movies are from recommendations.

# Types of recommendation systems:

## Collaborative Filtering
Collaborative filtering primarily relies on recorded **user-item interactions** to make recommendations. The core idea is to identify patterns and similarities among users based on their historical interactions with items. By leveraging this collective wisdom, the system can suggest items to a user based on the preferences of users who have shown similar behaviors or liked similar items in the past. It's effective when there's a substantial <u><i>user-item interaction history</u></i>. For example when we want to find a new movie to watch we’ll often ask our friends who share tastes similar to our own for recommendations.
<u><b>User-Based:</u></b> In this approach, the system identifies groups of users with similar preferences. If User A and User B have similar tastes, the system might recommend items to User A that User B bought or interacted with, and vice versa. For Example 'My Recommendations' section in Amazon displays recommended products based on our: past purchases and past interactions (visited products not yet purchased, search history, and so on)

![User-Based Collaborative Filtering](https://assets-global.website-files.com/60f03643ffba6a48a3bda298/6283567dd5e53d12f2bd1575_MeXlYz3B3hDgwKRyxKgt5E81tZrjGAJnRamktIFrBVn6vZt0NyK50a4MyS6WxP0Xy3E8CJPdAISoxxfiepg_nYKJQ9C4jovZhTClir3ljw_uAgqb9yZZv1Ksy7WZsAiUAW48mcFVvJTo8SlJSQ.png)

<u><b>Item-Based:</u></b> This approach focuses on the similarities between items rather than users. If User A liked Item X, and Item Y is similar to Item X based on user preferences, the system might recommend Item Y to User A. For Example, on visiting the product page for an Oculus VR headset, Amazon displays the following recommendations after the product information:

![Item-Based Collaborative Filtering 1](https://assets-global.website-files.com/60f03643ffba6a48a3bda298/6283567d699bda76d85c3f34_e4KkDVFSVE_J58_sFhtcG72Veg7eNymtDpgc0DYhk-yg3tJM1g9gqpGed08F4SMeDWOvUYpJSlV-g4uL3wUizBHS7lVbwFtH9RcOF2TKVntJqE3stTi6IlKaRC0OnXR-5QvgIp0cbbZ3J3dQNQ.png)

![Item-Based Collaborative Filtering 1](https://assets-global.website-files.com/60f03643ffba6a48a3bda298/6283567d003405907a14ccfe_hBFSRGTivdpH1hyf246uwK2wSjQ2BhHUXTdly-VK_flufNHyCkwlO-1b1f69wT5P0RD-CXYbCL9f2g1CS4Rf8xdwFdWChInvE6ju_iFmmRqwa0IsNUSPuIqwng_SrDPXn6bTEJvMYQ6_Fx7X7A.png)
 

**Pros of Collaborative Filtering:**
-  *Personalization:* Provides personalized recommendations which enhances the user experience.
-  *No Dependency on Item Attributes:* Unlike content-based filtering which needs detailed information about items, it doesn't rely on explicit item features.
-  *Serendipity:* It enables users to discover new items by leveraging the preferences of similar users.
-  *Adaptability to Changing Preferences:* Adapts to changes in user preferences over time.
  
**Cons of Collaborative Filtering:**
-  *Cold Start Problem:* Faces challenges when dealing with new users or items without sufficient interaction history.
-  *Sparsity of Data:* Users typically interact with only a small fraction of available items. This sparsity can lead to challenges in accurately identifying similar users.
-  *Popularity Bias:* Tends to recommend popular items more frequently, leading to a bias toward well-known or mainstream items.
-  *Scalability:* As the number of users and items grows, the computational complexity of finding similar users or items increases.

## Content-Based Filtering
Content-based filtering relies on extracting **relevant features** from items. These features could include textual content, keywords, genres, or any other attributes that describe the item's nature. Each user has a profile which is created by analyzing the features of items they have liked or interacted with. Content-based systems recommend items whose features match the user's profile. Platforms like Netflix analyze movie attributes (genres, directors, actors) to recommend films similar to ones users have enjoyed. Also, services like Spotify suggest songs based on genre, artist preferences, and even specific musical attributes like tempo or mood.

<p>Content-based filtering creates a profile for each user based on their preferences and interactions with items. But if the user is completely new there are some ways in which content-based systems handle this situation. It can prompt new users to explicitly specify their preferences or interests during the onboarding process (for example: Spotify). It might initialize a new user's profile with default or general preferences according to the demographic (for example: YouTube).The cold start problem is a challenge not only for collaborative filtering but also for content-based filtering, especially when dealing with completely new users who have not yet provided any interaction history.</p>
  
**Pros of Content-Based Filtering:**
-  *Personalization:* Provides highly personalized recommendations that align with the user's preferences.
-  *No Cold Start Problem for Items:* Even with limited user interaction data, the user profile can be created.
-  *Transparency:* Users can see an item's features and understand why it is recommended.
-  *Domain Independence:* Since it relies on item features, it adaptable to a wide range of domains. 

**Cons of Content-Based Filtering:**
-  *Limited Serendipity:* Since it recommends items with similar features, it struggles to introduce users to entirely new or unexpected items.
-  *Dependency on Rich Item Descriptions:* The performance of content-based filtering is closely tied to the availability of rich item descriptions and features. Any inaccuracy or sparsity in item description will compromise the model.
-  *Adaptability to Changing Preferences:* May not capture changing tastes over time as effectively as collaborative filtering.

## Hybrid Models
Hybrid models combine collaborative and content-based filtering to provide more accurate and diverse recommendation and eliminate their individual weaknesses. While collaborative filtering tends to recommend popular items, content-based filtering introduces variety by focusing on item features thus enabling diversity in hybrid models. Hybrid models can handle cold start problems, where there is limited data for new users or items. Hybrid models also incorporate contextual information, such as time, location, or user behavior, to make more relevant and timely recommendations. This adaptability enhances the user experience in dynamic scenarios.
<u><b>Types of Hybrid Models</u></b>

-  **Weighted Hybrid Models:** Assign weights to the recommendations generated by collaborative and content-based methods. The final recommendation is a combination of these weighted scores.

-  **Switching Hybrid Models:** Employ one method for certain scenarios or users and switch to another when necessary. The switch is based on predefined conditions or user characteristics.

-  **Feature Combination Hybrid Models:** Merge features from both collaborative and content-based methods to create a unified representation of items or users.

  

## Deep Learning Models
Neural networks and deep learning techniques have been increasingly applied to recommendation systems. These models can learn intricate patterns and relationships in large datasets, enhancing the quality of recommendations.

  
  
  

# Installation
To run the project, you'll need to have the following Python packages installed. You can install them using the following command:

```bash

pip install scikit-learn scipy pandas numpy matplotlib seaborn scikit-surprise

```

  

# About the Project

### Context
Online E-commerce websites like Amazon, Flipkart uses different recommendation models to provide personalized suggestions to different users. Amazon currently uses item-to-item collaborative filtering, which scales to massive data sets and produces high-quality recommendations in real-time.

### Objective
Build a recommendation system to recommend products to customers based on their previous ratings for other products.

### Features
The Amazon dataset contains the following attributes:

| Field      | Description                                         |
|------------|-----------------------------------------------------|
| userId     | Every user identified with a unique id             |
| productId  | Every product identified with a unique id          |
| Rating     | Rating of the corresponding product by the user    |
| timestamp  | Time of the rating (ignored for this exercise)     |



# License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](https://github.com/soumyadeepghoshGG/Recommendation%20Engine%20-%20Electronics%20in%20Amazon/blob/main/License.txt) file for details.


# Contact

For questions or issues, please contact me (Soumyadeep Ghosh) via mail: soumyadeepghosh57@gmail.com