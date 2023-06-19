# Resume
## Contact info
### Nikita Mordvinov
@thirdmadman as in discord, telegram an github
## About me
Self concentrated, engineer.
Accuracy, confidentiality my favorite rules.
Team is important part of my life, like a family.
## Skills
Git, HTML, CSS, JS, vue.js, PHP, Laravel, Java, Spring Boot, C++, Fusion 360, Photoshop, Ilustaor
Docker, Linux, bash
## Code examples
```
    public ArrayList<String> getTasksDedicId() {
        ArrayList<String> tasks = new ArrayList<>();
        HttpController http = new HttpController();
        Map<String, String> requestParams = new HashMap<>();
        try {
            requestParams = new HashMap<>();
            requestParams.put("out", "JSONdata");
            requestParams.put("auth", this.authToken);
            requestParams.put("func", "task");
            JSONArray tasksArray = null;
            String authContent = http.getHttpsReqWithData(GlobalSettings.getProperty("config.billmgrUrl"), requestParams);

            if (authContent.length() > 0) {
                String jsonNoChecked = authContent.replace(": null", "\"\"");
                tasksArray = new JSONArray(jsonNoChecked);
                if (tasksArray != null) {
                    for (int i = 0; i < tasksArray.length(); i++) {
                        JSONObject task = null;
                        try {
                            task = tasksArray.getJSONObject(i);
                            if (task.getString("itemtype_intname").equals("dedic")) {
                                tasks.add(task.getString("id"));
                            }
                        } catch (Exception e) {
                            log.log(Level.WARNING, "BILLMGR: getTasksDedicId: ERROR fetching JSON: some fields may be empty, id: [" + task.getString("id") + "]");
                        }
                    }
                    return tasks;
                }
            } else {
                log.log(Level.SEVERE, "BILLMGR: getTasksDedicId: Bad response of JSON - empty");
                System.out.println("No correct JSON found");
            }
        } catch (Exception e) {
            log.log(Level.SEVERE, "BILLMGR: getTasksDedicId: Failed to load JSON");
            e.printStackTrace();
        }
        return null;
    }
```
## Experience
NC (mano) java school project (teamlead, fullstack) https://github.com/nceduc-mano-tlt-org/2019-school-journal
## Education
TGU Electronics and nanoelectronics, mastery
NC java developer courses
## Languages
Russian(native language), English (Intermediate)
