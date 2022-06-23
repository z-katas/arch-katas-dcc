## Requirement Analysis
The following analyses follow the format:
*Given business requirement*
  * Initial Thoughts (if any)
  * NFRs (if any)
    * NFR 1
    * NFR 2



1. *The Platform must establish a way to incentivize engagement such as sharing of resources, collaboration, networking, facilitating introductions, and partnerships*
   * NPOs or candidates can be rewarded with points for various activities they perform using the system. [Google Maps Local Guides](https://maps.google.com/localguides/) is a good example which rewards with points on posting reviews, images, etc. on places. The Spotlight platform could also use something similar to award points to the NPOs and candidates on engagement.                                      
   * NFRs
     * **Configurability** - The platform must be configurable to introduce or update new incentive rules with minimum or no engineering effort to reward engagement.
2. *The Platform must categorize/tag nonprofit support services to match candidate needs identified in the onboarding assessment to include but not limited to Resume Writing Services, Interview Prep, Free Business Attire, Apprenticeship Program Registration, Training Program Registration, College & University Registration, Free Grocery & Meal Services, Discounted Rent & Housing Services, Daycare/Child Care Services, Mentorship/Career Advocate Services*
   * Allow tagging categories on NPO, NPO offerings, candidate profiles, etc.
   * NFRs
     * **Performance** - The platform must be performant to provide faster matches between NPO offerings and Candidates and provide relevant recommendations. Indexing categories on various data entities may help in this regard.
3. *End-Use Ease of Use is a hard requirement*
   * The underrepresented demographics may not be tech-savvy. So, the Spotlight App's IA should be simple and intuitive to improve engagement. The App could have tour guides, FAQs, etc. (Long-term) The Platform could push recommendations and notifications to enable the user to take the next step on the app.
   * To enable NPOs to integrate with the Spotlight platform, platform needs to have well defined and documented APIs.
   * NFRs
     * **Usability**
     * **Interoperability**
4. *Tracking candidate progress is a hard requirement.*
   * For NPOs which have their own APIs for their offerings, data must be regularly pulled from their APIs to update candidate progress and particular NPO offerings in the platform.
   * This warrants data integrity in the system to accurately show candidate progress as and when his course progress is updated.
   * NFRs
     * **Workflow**
     * **Data Integrity**
5. *Tracking engagement is a hard requirement*
   * Any activity (attending meetings, posts, subscribing to the offerings, etc.) performed by the users must be tracked and recorded in the system. This will also help to incentivize engagement. 
   * NFRs
     * **Workflow**
     * **Data Integrity**
6. *The Platform must provide a way to allow Non-Profits to publicize offerings to the platform that can provide some level of automatic matching for Candidate requests.*
   * Recommendations based on the candidate's profile, interests and activity in the system.
7. *The Platform allows offerings to contain rich text, links, and downloadable readable content such as PDFs, but no other downloads.*
   * Since the files/documents are essential for any NGO to operate, they must be safely stored and recoverable (in case of disaster).
   * NFRs
     * **Recoverability**
     * **Fault Tolerance**
8. *Each offering must support a certain list of properties (defined by the platform), such as name, organization description, website, unique identifier (assigned by the Administrators) and other identification information.*
9. *The Platform must provide both operational reports (number of candidate matches / period, number of offerings / region, and so on) and analytical reports (projections of future desirable career paths, Offering gaps in a region based on demand, and so on) for use by Administrators.*
    * System should reliably store user activity and data coming from various services in the platform.
    * Big data store to train models for better predictions on recommendations. Consider **OLAP solution** to perform analytics.
10. *Reminder to think critically about the nonprofit and candidate experience, anticipate these users needs while developing the use case and user stories. Consider what can offer these users maximum value to fulfill the intent of logging on the app.*
    *  Apply design thinking to understand user personas and their needs. Come up with a user experience that is intuitive.
    *  NFRs
       *  **Usability**
       
### Further Analysis and Considerations
#### Green Field Project
There are several factors which affect the success of any new business or green field project.
* Viability of the idea - Are there any buyers for the idea?
* Funding - Are there any investors for the idea? 
* Time - An idea may be viable but it may take a long time to develop / implement. And, an idea which is viable today may not be that attractive after certain period of time.

Also, _Why should the business invest to build a fortress when it is not sure if anyone would be staying in it or using it._

So, shorter iterations to get market feedback and pivoting, if necessary, becomes important. So, the architecture should be in such a way that it can evolve with the growth in the business.

**NFRs**
* **Feasibility**
* **Evolutionary**

#### Funding
The team researched about NPOs, 501 (c3), underrepresented demographics in the US. It was found that fund raising has been difficult during COVID times ([Source](https://morweb.org/post/5-challenges-facing-nonprofits-in-2021)) due to limited in-person fundraising opportunities. 

However, there were also articles stating that the Americans are generous ([Source](https://independentsector.org/about/the-charitable-sector/)) and donate to non-profits if their vision is sticky. Also, there are several grants for NPOs to raise money without taking out traditional business loans ([Source](https://www.fundera.com/blog/grants-for-nonprofits)). So, funding should not be a problem, at least in the long-term, if the Spotlight platform markets their idea and MVP faster. 

**NFRs**
* **Feasibility**

#### Security
Sensitive data stored in the system includes - Candidate career profiles, PII (email, phone, address, ethnicity, SSN, etc.). 
As per [GDPR](https://gdpr.eu/right-to-be-forgotten/), the system should be able to erase the PII if a user wants to be forgotten. 

Consider not leaving footprints of PII in various services and logs of the system, which might make it harder to erase the PII. Use just one place where the data can be stored and retrieved. Ephemeral storages, such as cache, may be used for faster retrievals but should have mechanisms in place to erase the data


#### No. of users and Regions

Going by the no. of NPOs ([Source](https://independentsector.org/about/the-charitable-sector/)) and under-represented demographics ([Source](https://www.governing.com/archive/gov-nonprofits.html)), there is a tremendous potential for active collaboration and could be an exponential growth in no. of users and NPOs in the platform once the idea is viral. Even if we assume 0.5% adoption in 1~2 years, there could be 100k NPOs and 500k under-represented folks using the platform, which is huge.

To support NPOs and demographics in multiple regions, consider multi-zone deployment in the longer-term, for improving availability.

**NFRs**
* Scalability
* Availability


### Summary 


| Given Requirements | Analysis | NFRs | 
| ------------------ | -------- | ---- |
| The Platform must establish a way to incentivize engagement such as sharing of resources, collaboration, networking, facilitating introductions, and partnerships| To introduce or update new incentive rules and rewards systems with no or minimal engineering effort | Configurability |
| The Platform must categorize/tag nonprofit support services to match candidate needs identified in the onboarding assessment | The platform must be performant to provide faster matches between NPO offerings and Candidates and provide relevant recommendations. Indexing categories on various data entities may help in this regard.| Performance |
| End-Use Ease of Use is a hard requirement | The underrepresented demographics may not be tech-savvy. So, the Spotlight App's Information Architecture should be simple and intuitive to improve engagement. To enable NPOs to integrate with the Spotlight platform, platform needs to have well defined and documented APIs. | Usability, Interoperability |
| Tracking candidate progress is a hard requirement. | For NPOs which have their own APIs for their offerings, data must be regularly pulled from their APIs to update candidate progress and particular NPO offerings in the platform. This warrants data integrity in the system to accurately show candidate progress as and when his course progress is updated.| Workflow, Data Integrity |
| Tracking engagement is a hard requirement | Any activity (attending meetings, posts, subscribing to the offerings, etc.) performed by the users must be tracked and recorded in the system. This will also help to incentivize engagement. | Workflow, Data Integrity | 
| The Platform must provide a way to allow Non-Profits to publicize offerings to the platform that can provide some level of automatic matching for Candidate requests. | Recommendations based on the candidate's profile, interests and activity in the system. | NA |
| The Platform allows offerings to contain rich text, links, and downloadable readable content such as PDFs, but no other downloads. | Since the files/documents are essential for any NGO to operate, they must be safely stored and recoverable (in case of disaster).  | Recoverability, Fault tolerance |
| The Platform must provide both operational reports (number of candidate matches / period, number of offerings / region, and so on) and analytical reports (projections of future desirable career paths, Offering gaps in a region based on demand, and so on) for use by Administrators. | System should reliably store user activity and data coming from various services in the platform. Big data store to train models for better predictions on recommendations. Consider **OLAP solution** to perform analytics.| NA | 
| Green Field Project | Green field projects need shorter iterations to get market feedback and pivoting, if necessary, becomes important. So, the architecture should allow faster introduction or removal of features. Also, raising funds has been difficult during COVID times.| Evolutionary, Feasibility | 
| [Derived] Sensitive data stored in the system includes - Candidate career profiles, PII (email, phone, address, ethnicity, SSN, etc.). | As per [GDPR](https://gdpr.eu/right-to-be-forgotten/), the system should be able to erase the PII if a user wants to be forgotten. | Security | 
| [Derived] No. of users | To support exponential growth in no. of users and NPOs in the platform once the idea is viral. Even if we assume 0.5% adoption (Reference - [NPOs](https://independentsector.org/about/the-charitable-sector/) and [Under-represented demographics](https://www.governing.com/archive/gov-nonprofits.html)) in 1-2 years, there could be 100k NPOs and 500k under-represented folks using the platform, which is huge.| Scalability |
| [Derived] Multi region support | To support NPOs and demographics in multiple regions, consider multi-zone deployment in the longer-term| Availability | 
