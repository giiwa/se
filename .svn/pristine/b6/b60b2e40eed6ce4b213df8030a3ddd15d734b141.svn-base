package org.giiwa.se.web;

import org.apache.commons.configuration2.Configuration;
import org.apache.commons.logging.Log;
import org.apache.commons.logging.LogFactory;
import org.giiwa.app.web.admin.dashboard;
import org.giiwa.app.web.admin.setting;
import org.giiwa.core.bean.X;
import org.giiwa.framework.bean.License;
import org.giiwa.framework.web.IListener;
import org.giiwa.framework.web.Module;
import org.giiwa.se.base.SE;
import org.giiwa.se.task.PerfMoniterTask;
import org.giiwa.se.web.admin.ess;

public class SeListener implements IListener {

	static Log log = LogFactory.getLog(SeListener.class);

	@Override
	public void onInit(Configuration conf, Module m) {

		log.info("webess is initing ...");

		m.setLicense(License.LICENSE.licensed,
				"FViqK8SlFwghyb16Hp5ferGHjVJ+YeKZ5lkm5DJoo9ZfH1TJqCCXD/IuCjAt2Hy0hzKQFa2X+Q2pJ/wv2kbzbYT5QZ8/Pgy0Y1pClqNbm8iz8+o9BHtKY0l5LNK4zlICFoxKdLDULvDcB9wm3pH+rRqmqPiw13z+lPw8eCP4648=");

		SE.init();

		setting.register("ess", ess.class);

		dashboard.portlet("/portlet/es/read");
		dashboard.portlet("/portlet/es/write");
		dashboard.portlet("/portlet/es/times");

	}

	@Override
	public void onStart(Configuration conf, Module m) {

		log.info("webess is starting ...");

		PerfMoniterTask.owner.schedule((long) (X.AMINUTE * Math.random()));
	}

	@Override
	public void onStop() {

		log.info("webess is stopping ...");

	}

	@Override
	public void uninstall(Configuration conf, Module m) {
		// TODO Auto-generated method stub

	}

	@Override
	public void upgrade(Configuration conf, Module m) {
		// TODO Auto-generated method stub

	}

}
