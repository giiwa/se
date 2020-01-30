package org.giiwa.se.web.admin;

import java.util.List;

import org.giiwa.core.bean.X;

import org.giiwa.core.conf.Global;
import org.giiwa.core.json.JSON;
import org.giiwa.framework.web.Path;
import org.giiwa.se.base.SE;

public class ess extends org.giiwa.app.web.admin.setting {

	@Override
	public void get() {

		List<JSON> l1 = SE.inst.indices();

		log.debug("l1=" + l1);

		this.set("list", l1);

		this.settingPage("/admin/ess.setting.html");

	}

	@Override
	public void set() {

		Global.setConfig("es.url", this.getString("es.url"));
		Global.setConfig("es.enabled", X.isSame(this.getString("es.enabled"), "on") ? 1 : 0);
		Global.setConfig("es.group", this.getString("es.group"));
		Global.setConfig("es.index.time", this.getString("es.index.time"));

		SE.GROUP = this.getString("es.group");

		this.response(JSON.create().append(X.STATE, 201).append(X.MESSAGE, lang.get("save.success")));
		return;
	}

	@Path(login = true, path = "delete", access = "access.config.admin")
	public void delete() {

		String name = this.getString("name");
		SE.inst.remove(name);
//		SE.inst.reset(name);
		this.response(JSON.create().append(X.STATE, 200).append(X.MESSAGE, lang.get("delete.success")));

	}

}
